# youtube-video-summariser

## Here's a rough step-by-step process:

**Transcription:** When the user inputs a YouTube URL, use AWS Lambda to call the Amazon Transcribe service and transcribe the video. <br>
**Summarization:** Pass the transcript to another Lambda function that uses the Amazon Bedrock text summarization model to generate a summary. <br>
**Audio Generation:** Send the summarized text to Amazon Polly to generate an audio file. <br>
**Storage:** Store the summarized text and audio file in an S3 bucket. <br>
**Frontend:** Develop a user interface using a frontend framework like React or Vue.js, where users can input the YouTube URL and retrieve the summarized text and audio. <br>
**API Gateway:** Use AWS API Gateway to connect your frontend with the Lambda functions and S3 bucket. <br>

You can use AWS Step Functions to orchestrate the entire workflow, making it easier to manage and monitor the process.

## Proof-of-concept (POC)

1. **Set up AWS Services**:
   - Create an AWS account and set up the required services: AWS Lambda, Amazon Transcribe, Amazon Bedrock, Amazon Polly, Amazon S3, AWS API Gateway, and AWS Step Functions.
   - Configure the necessary IAM roles and policies to allow these services to interact with each other.

2. **Video Transcription**:
   - Create an AWS Lambda function that accepts a YouTube video URL as input.
   - Use the `pytube` library (Python) or a similar library to download the video from the provided URL.
   - Call the Amazon Transcribe service to transcribe the video's audio into text.
   - Store the transcribed text in an S3 bucket.

3. **Text Summarization**:
   - Create another AWS Lambda function that reads the transcribed text from the S3 bucket.
   - Use the Amazon Bedrock text summarization model to generate a summary of the transcribed text.
   - Store the summarized text in a separate S3 bucket.

4. **Audio Generation**:
   - Create a third AWS Lambda function that reads the summarized text from the S3 bucket.
   - Call the Amazon Polly service to generate an audio file from the summarized text.
   - Store the generated audio file in the same S3 bucket as the summarized text.

5. **Orchestration with AWS Step Functions**:
   - Create an AWS Step Functions state machine to orchestrate the entire workflow.
   - Define the steps in the state machine to invoke the Lambda functions for transcription, summarization, and audio generation in the correct order.

6. **API Gateway and Frontend**:
   - Create an AWS API Gateway REST API that acts as the entry point for your application.
   - Define a POST method in the API Gateway that accepts a YouTube video URL as input.
   - Integrate the POST method with the AWS Step Functions state machine to trigger the workflow.
   - Develop a simple frontend (e.g., using React or Vue.js) that allows users to input a YouTube video URL and retrieve the summarized text and audio file.

7. **Testing and Deployment**:
   - Test your application locally using sample YouTube video URLs.
   - Deploy your application to AWS, including the frontend (e.g., using AWS Amplify or S3 static website hosting), API Gateway, Lambda functions, and other resources.
   - Test the deployed application with different YouTube video URLs.


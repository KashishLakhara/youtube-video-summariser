# youtube-video-summariser

Here's a rough step-by-step process:

**Transcription:** When the user inputs a YouTube URL, use AWS Lambda to call the Amazon Transcribe service and transcribe the video. <br>
**Summarization:** Pass the transcript to another Lambda function that uses the Amazon Bedrock text summarization model to generate a summary. <br>
**Audio Generation:** Send the summarized text to Amazon Polly to generate an audio file. <br>
**Storage:** Store the summarized text and audio file in an S3 bucket. <br>
**Frontend:** Develop a user interface using a frontend framework like React or Vue.js, where users can input the YouTube URL and retrieve the summarized text and audio. <br>
**API Gateway:** Use AWS API Gateway to connect your frontend with the Lambda functions and S3 bucket. <br>

You can use AWS Step Functions to orchestrate the entire workflow, making it easier to manage and monitor the process.

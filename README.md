# Create a serverless Solution  AWS Lambda and Amazon Transcribe
1. Create an IAM role which will be utilized by the Lambda function 
![](./img/01create%20iamrole.png)
2. Trust Entity type, choose AWS Service and choose Lambda under the use case
![](./img/02-choose-lambda.png)
3. Grant permissions to the role. the permissions required for these are<br>
    - S3 full access permission
    ![](./img/03-s3access.png)
    - Transcribe Full access
    ![](./img/04transcribeaccess.png/)
    - Cloudwatch full access
    ![](./img/05cloudwatch.png)
4. Give a name to the role 
![](./img/06-rolename.png)
5. Search for Lambda under services
6. Create a function, choose Author from scratch, fill in the function name and specify the runtime. In ths case, we use python for the runtime
![](./img/07lambdafunction.png)
7. Change the default execution role and choose an existing role, from the dropdown menu, choose the role that was initially created
![](./img/08chooserole.png)
8. Under the code source section, delete the default code, paste the new code and click deploy 
![](./img/09update-code.png)
9. Search for S3 under services, and create a new S3 bucket using a unique name for the bucket
![](./img/10create%20bucket.png)
10. Click on your newly created bucket
![](./img/11clickbucket.png)
11. Go to the properties tab of your bucket 
![](./img/12properties.png)
12. Under the properties tab, go to Event notifications and create an event notification
![](./img/13createeventnotification.png)
13. Enter an event name and a suffix for the type of file to use
![](./img/14name&suffix.png)
14. Under the event types, select 'All Object create events'
![](./img/15tick%20this.png)
15. Scroll to destination and select lambda function and from the dropdown menu, choose your function
![](./img/16destination.png)
16. Go to objects and upload your file, this is the audio file that you intend to transcribe. 
![](./img/17objects.png)
![](./img/18upload.png)
17. Search for CloudWatch under services, locate logs at the side menu and choose Log groups 
![](./img/19cloudwatch.png)
18. You will find log groups, click on the newly created log group 
![](./img/20log-group.png)
19. You will see the log stream, click the log stream to view the log 
![](./img/21logstream.png)
![](./img/22logstreamview.png)
20. Search for Amazon Transcribe from the services menu, on the side bar, there is transcription jobs, click on it
![](./img/23transcribe.png)
21. you will see a job with status complete
![](./img/24thejob.png)
22. In the job details, you will the output data location.
![](./img/25outputlocation.png)
23. Back to S3 bucket, click on your bucket 
![](./img/26insidethebucket.png)
24. Inside the bucket, you will see a newly created folder called transcripts
![](./img/27transcript.png)
25. Open the transcripts folder and download the file 
![](./img/28download.png)
26. Using Gtbash for windows or terminal, change the directory to the directory where the file was downloaded, then run the python command on the file 
![](./img/29run-command.png)
27. There you will see the transcript of the audio file 
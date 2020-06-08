# s3-to-syslog
CloudFormation template for sending S3 logs to Syslog.

 **Important note:**  the lambda created in this template will need to have an S3 event configured to trigger it - this is not done for you in this template, you will need to [follow the steps here](https://docs.aws.amazon.com/AmazonS3/latest/user-guide/enable-event-notifications.html/) for the lambda to work.


This template will create a lambda which is attached to a VPC.  The lambda is triggered by an S3 event notification for whichever bucket you need to send to Syslog.  The lambda will reach new objects as they are created and send them to the Syslog server specified in the CloudFormation parameters (this template assumes that the Syslog server is running on port 514).


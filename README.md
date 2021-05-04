# covinfo India

Send hourly email notifications about vaccination sessions.

Built using AWS Services and requires an AWS Account to deploy Cloudformation template.

To deploy

A] Verify recipient email in SES
1. Login to AWS Console in Mumbai(ap-south-1) Region
2. Verify email: https://docs.aws.amazon.com/ses/latest/DeveloperGuide/verify-email-addresses-procedure.html

B] Deploy Stack
1. Login to AWS Console in Mumbai(ap-south-1) Region
2. Navigate to Cloudformation service and deploy 'Template.yaml'

Stack works in Mumbai region only due to cowin API nature.

Resources created by stack:
* GetCowinfoLambdaFunction

   Lambda function to fetch vaccination slot information using cowin API and send email using SES

* GetCowinfoRole

   IAM role for GetCowinfoLambdaFunction

* ScheduledRule

   Events rule to invoke GetCowinfoLambdaFunction every 60 minutes

* PermissionForEventsToInvokeLambda

   To allow ScheduledRule invoke GetCowinfoLambdaFunction

\
API reference: https://apisetu.gov.in/public/api/cowin
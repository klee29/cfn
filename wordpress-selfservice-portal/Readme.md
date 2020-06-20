This project is part of cloudformation with practical example which is wordpress website. 
Especially, this project works with external gederate identity (with Google Auth) concept. 

- There are two portion customer, and service provider(business)
- This is worked through about that how this project is working on below:
  1. Client sent a 'order now' request --> Backend order processing
  2. Backend order processing --> Support (or hosting) team 
  3. Support team get resource from 'Portal bucket'(S3); provisionbucket.yaml
  4. Uses CloudFormation, and it tries to get resource from 'Resource Bucket'(S3); create bucket stack via cloudformation
  5. Create Stack, which gets proper permission from AWS-IAM
  6. Send a notification to customer about created a stack 
  7. Customer get credential from External Federate Identification (Google Auth); [Google API Manager](https://console.developers.google.com/projectselector2/apis/dashboard?pli=1&supportedpurview=project);, OAuth Client Id in Credential section, put 'selfservicebucket(S3 from AWS)' URL at OAuth client. 
  --> Send it to AWS-Congnito
  8. With STS-Token(which is temporary credential) from Cognito, customer interacts with Stack 
  



# Cross-account operations

## Problem

We recommend, in general, that you use multiple accounts. This is on the one 
hand for dealing with per-account limits, also known as [Service Quotas](https://docs.aws.amazon.com/servicequotas/latest/userguide/intro.html) 
, and on the other hand it helps with strengthening the [security posture](https://d0.awsstatic.com/aws-answers/AWS_Multi_Account_Security_Strategy.pdf).

The question is now, how and where are cross-account operations supported? 

## Solutions

https://aws.amazon.com/blogs/aws/new-aws-resource-access-manager-cross-account-resource-sharing/

https://aws.amazon.com/blogs/compute/managing-cross-account-serverless-microservices/

### IAM

[Permissions across accounts](https://youtu.be/Zvz-qYYhvMk?t=2852) (a re:Invent 2019 talk by Becky Weiss

https://docs.aws.amazon.com/IAM/latest/UserGuide/tutorial_cross-account-with-roles.html

https://aws.amazon.com/blogs/security/how-to-enable-cross-account-access-to-the-aws-management-console/

https://n2ws.com/blog/aws-cloud/managing-aws-accounts-cross-account-iam-roles

https://aws.amazon.com/blogs/apn/securely-accessing-customer-aws-accounts-with-cross-account-iam-roles/

https://aws.amazon.com/blogs/security/tag/cross-account-access/

### Compute
https://aws.amazon.com/premiumsupport/knowledge-center/secondary-account-access-ecr/

https://stackoverflow.com/questions/38128884/cross-account-role-for-an-aws-lambda-function

### Networking

https://aws.amazon.com/blogs/networking-and-content-delivery/vpc-sharing-a-new-approach-to-multiple-accounts-and-vpc-management/

### Data
https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-s3/

https://stelligent.com/2016/07/12/cross-account-access-control-with-amazon-sts-for-dynamodb/

## Conclusion

Using multiple accounts, while recommended, can be challenging. Using available
tools and managed services along with applying good practices makes it a
possible to strengthening your defense-in-depth and also overcome account limits.

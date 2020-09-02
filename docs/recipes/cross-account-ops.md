# Cross-account operations

## Problem

We recommend, in general, that you use multiple accounts. This is on the one 
hand for dealing with per-account limits, also known as [Service Quotas](https://docs.aws.amazon.com/servicequotas/latest/userguide/intro.html) 
, and on the other hand it helps with strengthening the [security posture](https://d0.awsstatic.com/aws-answers/AWS_Multi_Account_Security_Strategy.pdf).

The question is now how and where are cross-account operations supported? 

## Solutions

Cross-account operations apply in principle to all services. This doesn't mean
that all services support it out of the box. It usually boils down to  

For a general introduction into the topic you, check out Becky Weiss' re:Invent 2019
talk on [permissions across accounts](https://youtu.be/Zvz-qYYhvMk?t=2852).

 
First off, you have to try and understand [how IAM roles differ from 
resource-based Policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_compare-resource-policies.html):


> Cross-account access with a resource-based policy has some advantages over
> cross-account access with a role. With a resource that is accessed through 
> a resource-based policy, the principal still works in the trusted account
> and does not have to give up his or her permissions to receive the role 
> permissions. In other words, the principal continues to have access to
> resources in the trusted account at the same time as he or she has access
> to the resource in the trusting account.

So, resource-based policies are attached to a resource while identity-based 
policies are attached to an IAM user, group, or role, with the principal (*who*
is allowed to do something) implicitly set by the entity the policy is attached
to.

Finally, do some hands-on with the tutorial on [delegating access across AWS 
accounts using IAM Roles](https://docs.aws.amazon.com/IAM/latest/UserGuide/tutorial_cross-account-with-roles.html) 
and check out [how to enable cross-account access to the console](https://aws.amazon.com/blogs/security/how-to-enable-cross-account-access-to-the-aws-management-console/).

Let's have a look at some service-specific recipes now.

Compute (covering EC2, container services like ECS/EKS/ECR, as well as Lambda):

- [Enabling cross-account access to Amazon EKS cluster resources](https://aws.amazon.com/blogs/containers/enabling-cross-account-access-to-amazon-eks-cluster-resources/)
- [Improve Operational Efficiency with Cross-Account AWS IAM Roles in ECS Containers](https://www.nclouds.com/blog/improve-operational-efficiency-cross-account-aws-iam-roles-ecs-containers/)
- [Allow secondary account to push to/pull from ECR repository](https://aws.amazon.com/premiumsupport/knowledge-center/secondary-account-access-ecr/)
- [Cross account access for Lambda functions](https://stackoverflow.com/questions/38128884/cross-account-role-for-an-aws-lambda-function)
- [Managing Cross-Account Serverless Microservices](https://aws.amazon.com/blogs/compute/managing-cross-account-serverless-microservices/)


Networking-related:

- [VPC sharing: A new approach to multiple accounts and VPC management](https://aws.amazon.com/blogs/networking-and-content-delivery/vpc-sharing-a-new-approach-to-multiple-accounts-and-vpc-management/)
- [Using VPC Sharing for a Cost-Effective Multi-Account Microservice Architecture](https://aws.amazon.com/blogs/architecture/using-vpc-sharing-for-a-cost-effective-multi-account-microservice-architecture/)

Data and storage topics:

- [How can I provide cross-account access to objects that are in S3 buckets?](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-s3/)
- [How can I grant my EC2 instance access to an S3 bucket in another account?](https://aws.amazon.com/premiumsupport/knowledge-center/s3-instance-access-bucket/)
- [Cross-Account Access Control with Amazon STS for DynamoDB](https://stelligent.com/2016/07/12/cross-account-access-control-with-amazon-sts-for-dynamodb/)

## Further reading

- Posts on the AWS Security Blog:
    - tagged with [cross-account access](https://aws.amazon.com/blogs/security/tag/cross-account-access/)
    - tagged with [Resource-based policies](https://aws.amazon.com/blogs/security/tag/resource-based-policies/)
- [New AWS Resource Access Manager – Cross-Account Resource Sharing](https://aws.amazon.com/blogs/aws/new-aws-resource-access-manager-cross-account-resource-sharing/)
- [Securely Accessing Customer AWS Accounts with Cross-Account IAM Roles](https://aws.amazon.com/blogs/apn/securely-accessing-customer-aws-accounts-with-cross-account-iam-roles/)

## Conclusion

Using multiple accounts, while recommended, can be challenging. Using available
tools and managed services along with applying good practices makes it a
possible to strengthening your defense-in-depth and also overcome account limits.

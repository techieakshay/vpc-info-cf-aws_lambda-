# AWS CloudFormation - Lambda Function to Fetch VPC Information

This CloudFormation template deploys a **Lambda function** that retrieves and outputs details about the **Amazon VPC (Virtual Private Cloud)**, including subnets, route tables, security groups, and other VPC-related metadata. This Lambda function can be triggered on demand to fetch VPC information and log it to **Amazon CloudWatch**.

## Features
- **AWS Lambda Function**: A serverless function to query the VPC details.
- **IAM Role**: The Lambda function has an attached IAM role with the necessary permissions to query VPC resources.
- **CloudWatch Logs**: Logs the results of the VPC query to CloudWatch for easy access and debugging.
- **AWS SDK Integration**: Uses the AWS SDK for JavaScript (Node.js) to query VPC resources.
  
## Architecture
The stack consists of:
1. **Lambda Function**: Queries VPC-related information.
2. **IAM Role**: Grants the Lambda function the necessary permissions to describe VPC resources.
3. **CloudWatch Logs**: Stores logs generated by the Lambda function.

## Prerequisites
- AWS CLI or access to the AWS Console.
- IAM permissions to create Lambda functions, IAM roles, and log groups.
- Node.js for local testing and development (optional).

## Deployment Instructions

### 1. Deploy the CloudFormation Stack

#### Using AWS CLI
You can also create the stack using the AWS CLI:
```bash
aws cloudformation create-stack --stack-name VpcInfoLambdaStack --template-body file://cftemplate.json --capabilities CAPABILITY_NAMED_IAM --profile  my-profile 

    ** Replace the profile with your profile

#### Using the function
- Call the lambda with the below payload
    Payload :: 
 
    {
        "vpcId" : "YOUR VPC ID"
    }

    ** This will output you the VPC Info               
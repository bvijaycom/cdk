cdk installtion

    Requiremnets

        - ubuntu machine ( x64 )

Packages:
        
    sudo apt update
    sudo apt install python3 python3-pip -y
    
Install cdk installtion:
        
    pip3 install aws-cdk.cdk 
    pip3 install awscli

verify cdk installtion:

    cdk --version

configure aws credentials:

    aws configure

Stack Details:

    S3bucketStack

        1. Create S3 bucket
        2. Upload the file into s3 bucket

    LambdaCronStack

        1. create iam role ( dynamdb:*, s3bucket:*, cloudwatch:*, lambda:* )
        2. Lambdafunction Create
        3. Create event trigger function in cloudwatch

    DynamoDbStack

        1. Create dynamodb

Deploy procedures
    
    cdk bootstrap ( Deploys the CDK toolkit stack into an AWS environment )

    cdk bootstrap -b [backetname] (To specify the s3 bucket name)

    cdk list
    cdk synthesize  

parameter passing methods

    cdk deploy  \
        --parameters uploadBucketName=jinojoes3bucket \
        --parameters LambdaName=jinojoelambda \
        --parameters DynamodbName=jinojoeDynamodb

Reference: 

- https://docs.aws.amazon.com/cdk/api/latest/python/aws_cdk.aws_lambda/Function.html

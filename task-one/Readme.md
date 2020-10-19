Stack Details:
    
    S3bucketRule

        1. Create S3 bucket
        2. Upload the file into s3 bucket

    LambdaCronRule

        1. create iam role ( dynamdb:*, s3bucket:*, cloudwatch:*, lambda:* )
        2. Lambdafunction Create
        3. Create event trigger function in cloudwatch

    DynamoDbRule

        1. Create dynamodb

Deploy procedures
    
    cdk bootstrap -b [unique s3backetname] ( Deploys the CDK toolkit stack into an AWS environment )
    cdk list
    cdk synthesize  

parameter passing methods

    cdk deploy  \
        --parameters uploadBucketName=jinojoes3bucket \
        --parameters LambdaName=jinojoelambda \
        --parameters DynamodbName=jinojoeDynamodb \
        --parameters uploadZipfileName=./lambdafiles \
        --parameters targetFoldername='web/static'
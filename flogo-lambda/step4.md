Great! So we've built the zip that we need to deploy to Lambda and that is exactly what we'll do in this step.

#### IAM policies and roles
Generally speaking it is a good idea to create separate IAM users for deploying to AWS. This allows you to explicitly control which resources a Lambda function can use. For now, you can make use of any IAM user that has the ability to deploy to AWS Lambda and you'll need the Access Key ID and Secret Access Key for this step.

As you go on with building apps for Lambda we do strongly recommend looking atht the [AWS IAM documentation](http://docs.aws.amazon.com/IAM/latest/UserGuide/introduction_access-management.html) to find out which policies you need to set for your IAM user.

For this tutorial we'll also assume that you have an IAM role with enough permissions to create a Lambda function. If you've used the AWS Lambda console, there will likely be an IAM role called **lambda_basic_execution** which you can use for this tutorial. In any case you'll need the ARN of this role later in this step (which you can find in the IAM console).

#### Configure AWS CLI
Run the command `aws configure`{{execute}} to start the configuration of your AWS CLI (_please note that we do **not** store any credentials_). You'll be asked to provide:

* AWS Access Key ID
* AWS Secret Access Key
* Default region name (the region you want to deploy to, like `us-west-2`)
* Default output format (the output format you want, like `json`)

#### Deploy your app
To deploy your app go to the directory where the zip was created (`cd /home/scrapbook/tutorial/myapp/src/myapp`{{execute}}). From here you can execute the command `aws lambda create-function --function-name tutorial --runtime go1.x --role arn:aws:iam::<account>:role/<role name> --handler handler --zip-file "fileb://handler.zip"`{{execute}}. This will create a new function in Lambda called _tutorial_, which uses the Go runtime. The _--role arn:aws:iam::<account>:role/<role name>_ is the full ARN of the IAM role used to deploy this function. If all went well you'll see a JSON response like this:
```json
{
    "TracingConfig": {
        "Mode": "PassThrough"
    },
    "CodeSha256": "KzHoXLnTXi9uMugXAOLrMHq6qJ6RimzYdNfrWXIxwLw=",
    "FunctionName": "tutorial",
    "CodeSize": 4026592,
    "RevisionId": "94b184e5-74e3-4881-abf5-debad47541b5",
    "MemorySize": 128,
    "FunctionArn": "arn:aws:lambda:<region>:<account>:function:tutorial",
    "Version": "$LATEST",
    "Role": "arn:aws:iam::<account>:role/<role>",
    "Timeout": 3,
    "LastModified": "2018-05-12T19:30:41.116+0000",
    "Handler": "handler",
    "Runtime": "go1.x",
    "Description": ""
}
```
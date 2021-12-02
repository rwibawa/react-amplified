# react-amplified
* [Tutorial](https://docs.amplify.aws/start/getting-started/setup/q/integration/react/#create-a-new-react-app)

## 1. Setup
### 1.1. Create a new reactjs app:
```sh
$ nvm ls
  * 12.22.7 (Currently using 64-bit executable)
$ npm install -g @aws-amplify/cli

$ npx create-react-app react-amplified
$ cd react-amplified

$ yarn start

```

### 1.2. Create the back-end:
```sh
$ amplify init
Note: It is recommended to run this command from the root of your app directory
? Enter a name for the project react-amplified
>> Project name should be between 3 and 20 characters and alphanumeric
E:\workspace_amplify>amplify configure
Follow these steps to set up access to your AWS account:

Sign in to your AWS administrator account:
https://console.aws.amazon.com/
Press Enter to continue

Specify the AWS Region
? region:  us-west-1
Specify the username of the new IAM user:
? user name:  amplify-mFkzo
Complete the user creation using the AWS console
https://console.aws.amazon.com/iam/home?region=us-west-1#/users$new?step=final&accessKey&userNames=amplify-mFkzo&permissionType=policies&policies=arn:aws:iam::aws:policy%2FAdministratorAccess
Press Enter to continue

Enter the access key of the newly created user:
? accessKeyId:  ********************
? secretAccessKey:  ****************************************
This would update/create the AWS Profile in your local machine
? Profile Name:  default

Successfully set up the new user.


$ amplify init
Note: It is recommended to run this command from the root of your app directory
? Enter a name for the project reactamplified
The following configuration will be applied:

Project information
| Name: reactamplified
| Environment: dev
| Default editor: Visual Studio Code
| App type: javascript
| Javascript framework: react
| Source Directory Path: src
| Distribution Directory Path: build
| Build Command: npm.cmd run-script build
| Start Command: npm.cmd run-script start

? Initialize the project with the above configuration? Yes
Using default provider  awscloudformation
? Select the authentication method you want to use: AWS profile

For more information on AWS Profiles, see:
https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-profiles.html

? Please choose the profile you want to use default
Adding backend environment dev to AWS Amplify app: dtvgqrv328pxw
- Initializing project in the cloud...

CREATE_IN_PROGRESS amplify-reactamplified-dev-162717 AWS::CloudFormation::Stack Wed Dec 01 2021 16:27:26 GMT-0800 (Pacific Standard Time) User Initiated
CREATE_IN_PROGRESS DeploymentBucket                  AWS::S3::Bucket            Wed Dec 01 2021 16:27:29 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS AuthRole                          AWS::IAM::Role             Wed Dec 01 2021 16:27:29 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS UnauthRole                        AWS::IAM::Role             Wed Dec 01 2021 16:27:30 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS UnauthRole                        AWS::IAM::Role             Wed Dec 01 2021 16:27:31 GMT-0800 (Pacific Standard Time) Resource creation Initiated
\ Initializing project in the cloud...

CREATE_IN_PROGRESS DeploymentBucket AWS::S3::Bucket Wed Dec 01 2021 16:27:31 GMT-0800 (Pacific Standard Time) Resource creation Initiated
- Initializing project in the cloud...

CREATE_IN_PROGRESS AuthRole AWS::IAM::Role Wed Dec 01 2021 16:27:31 GMT-0800 (Pacific Standard Time) Resource creation Initiated
/ Initializing project in the cloud...

CREATE_COMPLETE UnauthRole AWS::IAM::Role Wed Dec 01 2021 16:27:44 GMT-0800 (Pacific Standard Time)
CREATE_COMPLETE AuthRole   AWS::IAM::Role Wed Dec 01 2021 16:27:45 GMT-0800 (Pacific Standard Time)
/ Initializing project in the cloud...

CREATE_COMPLETE DeploymentBucket                  AWS::S3::Bucket            Wed Dec 01 2021 16:27:52 GMT-0800 (Pacific Standard Time)
CREATE_COMPLETE amplify-reactamplified-dev-162717 AWS::CloudFormation::Stack Wed Dec 01 2021 16:27:54 GMT-0800 (Pacific Standard Time)
√ Successfully created initial AWS cloud resources for deployments.
√ Initialized provider successfully.
Initialized your environment successfully.

Your project has been successfully initialized and connected to the cloud!

Some next steps:
"amplify status" will show you what you've added already and if it's locally configured or deployed
"amplify add <category>" will allow you to add features like user login or a backend API
"amplify push" will build all your local backend resources and provision it in the cloud
"amplify console" to open the Amplify Console and view your project status
"amplify publish" will build all your local backend and frontend resources (if you have hosting category added) and provision it in the cloud

Pro tip:
Try "amplify add api" to create a backend API and then "amplify publish" to deploy everything

$ yarn add aws-amplify @aws-amplify/ui-react@1.x.x
```
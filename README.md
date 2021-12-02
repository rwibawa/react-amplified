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

### 1.3. Create a GraphQL API and database
```sh
$ amplify add api
? Select from one of the below mentioned services: GraphQL
? Here is the GraphQL API that we will create. Select a setting to edit or continue Continue
? Choose a schema template: Single object with fields (e.g., “Todo” with ID, name, description)

⚠️  WARNING: your GraphQL API currently allows public create, read, update, and delete access to all models via an API Key. To configure PRODUCTION-READY a
uthorization rules, review: https://docs.amplify.aws/cli/graphql/authorization-rules

GraphQL schema compiled successfully.

Edit your schema at E:\workspace_amplify\react-amplified\amplify\backend\api\reactamplified\schema.graphql or place .graphql files in a directory at E:\workspace_amplify\react-amplified\amplify\backend\api\reactamplified\schema
√ Do you want to edit the schema now? (Y/n) · yes
? Choose your default editor: Visual Studio Code
Edit the file in your editor: E:\workspace_amplify\react-amplified\amplify\backend\api\reactamplified\schema.graphql
✅ Successfully added resource reactamplified locally

✅ Some next steps:
"amplify push" will build all your local backend resources and provision it in the cloud
"amplify publish" will build all your local backend and frontend resources (if you have hosting category added) and provision it in the cloud


$ amplify push
/ Fetching updates to backend environment: dev from the cloud.
⚠️  WARNING: your GraphQL API currently allows public create, read, update, and delete access to all models via an API Key. To configure PRODUCTION-READY a
uthorization rules, review: https://docs.amplify.aws/cli/graphql/authorization-rules

GraphQL schema compiled successfully.

Edit your schema at E:\workspace_amplify\react-amplified\amplify\backend\api\reactamplified\schema.graphql or place .graphql files in a directory at E:\workspace_amplify\react-amplified\amplify\backend\api\reactamplified\schema
√ Successfully pulled backend environment dev from the cloud.
- Building resource api/reactamplified
⚠️  WARNING: your GraphQL API currently allows public create, read, update, and delete access to all models via an API Key. To configure PRODUCTION-READY a
uthorization rules, review: https://docs.amplify.aws/cli/graphql/authorization-rules

GraphQL schema compiled successfully.

Edit your schema at E:\workspace_amplify\react-amplified\amplify\backend\api\reactamplified\schema.graphql or place .graphql files in a directory at E:\workspace_amplify\react-amplified\amplify\backend\api\reactamplified\schema

    Current Environment: dev

┌──────────┬────────────────┬───────────┬───────────────────┐
│ Category │ Resource name  │ Operation │ Provider plugin   │
├──────────┼────────────────┼───────────┼───────────────────┤
│ Api      │ reactamplified │ Create    │ awscloudformation │
└──────────┴────────────────┴───────────┴───────────────────┘
? Are you sure you want to continue? Yes

⚠️  WARNING: your GraphQL API currently allows public create, read, update, and delete access to all models via an API Key. To configure PRODUCTION-READY a
uthorization rules, review: https://docs.amplify.aws/cli/graphql/authorization-rules

GraphQL schema compiled successfully.

Edit your schema at E:\workspace_amplify\react-amplified\amplify\backend\api\reactamplified\schema.graphql or place .graphql files in a directory at E:\workspace_amplify\react-amplified\amplify\backend\api\reactamplified\schema
| Building resource api/reactamplified
⚠️  WARNING: your GraphQL API currently allows public create, read, update, and delete access to all models via an API Key. To configure PRODUCTION-READY a
uthorization rules, review: https://docs.amplify.aws/cli/graphql/authorization-rules

GraphQL schema compiled successfully.

Edit your schema at E:\workspace_amplify\react-amplified\amplify\backend\api\reactamplified\schema.graphql or place .graphql files in a directory at E:\workspace_amplify\react-amplified\amplify\backend\api\reactamplified\schema
? Do you want to generate code for your newly created GraphQL API Yes
? Choose the code generation language target javascript
? Enter the file name pattern of graphql queries, mutations and subscriptions src\graphql\**\*.js
? Do you want to generate/update all possible GraphQL operations - queries, mutations and subscriptions Yes
? Enter maximum statement depth [increase from default if your schema is deeply nested] 2
/ Updating resources in the cloud. This may take a few minutes...

UPDATE_IN_PROGRESS amplify-reactamplified-dev-162717 AWS::CloudFormation::Stack Wed Dec 01 2021 16:40:08 GMT-0800 (Pacific Standard Time) User Initiated
CREATE_IN_PROGRESS apireactamplified                 AWS::CloudFormation::Stack Wed Dec 01 2021 16:40:13 GMT-0800 (Pacific Standard Time)
/ Updating resources in the cloud. This may take a few minutes...

CREATE_IN_PROGRESS apireactamplified AWS::CloudFormation::Stack Wed Dec 01 2021 16:40:14 GMT-0800 (Pacific Standard Time) Resource creation Initiated
- Updating resources in the cloud. This may take a few minutes...

CREATE_IN_PROGRESS amplify-reactamplified-dev-162717-apireactamplified-L8DTJHF2K7KE AWS::CloudFormation::Stack Wed Dec 01 2021 16:40:14 GMT-0800 (Pacific Standard Time) User Initiated
/ Updating resources in the cloud. This may take a few minutes...

CREATE_IN_PROGRESS GraphQLAPI AWS::AppSync::GraphQLApi Wed Dec 01 2021 16:40:40 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS GraphQLAPI AWS::AppSync::GraphQLApi Wed Dec 01 2021 16:40:42 GMT-0800 (Pacific Standard Time) Resource creation Initiated
CREATE_COMPLETE    GraphQLAPI AWS::AppSync::GraphQLApi Wed Dec 01 2021 16:40:42 GMT-0800 (Pacific Standard Time)
/ Updating resources in the cloud. This may take a few minutes...

CREATE_IN_PROGRESS GraphQLAPITransformerSchema3CB2AE18 AWS::AppSync::GraphQLSchema Wed Dec 01 2021 16:40:44 GMT-0800 (Pacific Standard Time)

CREATE_IN_PROGRESS GraphQLAPIDefaultApiKey215A6DD7     AWS::AppSync::ApiKey        Wed Dec 01 2021 16:40:44 GMT-0800 (Pacific Standard Time)

CREATE_IN_PROGRESS GraphQLAPINONEDS95A13CF0            AWS::AppSync::DataSource    Wed Dec 01 2021 16:40:45 GMT-0800 (Pacific Standard Time)

CREATE_IN_PROGRESS GraphQLAPITransformerSchema3CB2AE18 AWS::AppSync::GraphQLSchema Wed Dec 01 2021 16:40:46 GMT-0800 (Pacific Standard Time) Resource creation Initiated
CREATE_COMPLETE    GraphQLAPITransformerSchema3CB2AE18 AWS::AppSync::GraphQLSchema Wed Dec 01 2021 16:40:47 GMT-0800 (Pacific Standard Time)

/ Updating resources in the cloud. This may take a few minutes...

CREATE_IN_PROGRESS GraphQLAPINONEDS95A13CF0        AWS::AppSync::DataSource Wed Dec 01 2021 16:40:57 GMT-0800 (Pacific Standard Time) Resource creation Initiated
CREATE_IN_PROGRESS GraphQLAPIDefaultApiKey215A6DD7 AWS::AppSync::ApiKey     Wed Dec 01 2021 16:40:57 GMT-0800 (Pacific Standard Time) Resource creation Initiated
CREATE_COMPLETE    GraphQLAPINONEDS95A13CF0        AWS::AppSync::DataSource Wed Dec 01 2021 16:40:57 GMT-0800 (Pacific Standard Time)

CREATE_COMPLETE    GraphQLAPIDefaultApiKey215A6DD7 AWS::AppSync::ApiKey     Wed Dec 01 2021 16:40:57 GMT-0800 (Pacific Standard Time)

/ Updating resources in the cloud. This may take a few minutes...

CREATE_IN_PROGRESS Todo AWS::CloudFormation::Stack Wed Dec 01 2021 16:40:59 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS Todo AWS::CloudFormation::Stack Wed Dec 01 2021 16:41:00 GMT-0800 (Pacific Standard Time) Resource creation Initiated
- Updating resources in the cloud. This may take a few minutes...

CREATE_IN_PROGRESS amplify-reactamplified-dev-162717-apireactamplified-L8DTJHF2K7KE-Todo-1FEC0XL5N2MR9 AWS::CloudFormation::Stack Wed Dec 01 2021 16:41:00 
GMT-0800 (Pacific Standard Time) User Initiated
| Updating resources in the cloud. This may take a few minutes...

CREATE_IN_PROGRESS SubscriptionOnUpdateTodoDataResolverFnSubscriptionOnUpdateTodoDataResolverFnAppSyncFunction523DF0E4       AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:07 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS SubscriptionOnCreateTodoDataResolverFnSubscriptionOnCreateTodoDataResolverFnAppSyncFunction462A70C9       AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:07 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS MutationcreateTodoinit0FunctionMutationcreateTodoinit0FunctionAppSyncFunction54DE5B8B                     AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:07 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS TodoTable                                                                                                 AWS::DynamoDB::Table
      Wed Dec 01 2021 16:41:07 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS TodoIAMRole2DA8E66E                                                                                       AWS::IAM::Role
      Wed Dec 01 2021 16:41:07 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS QuerygetTodopostAuth0FunctionQuerygetTodopostAuth0FunctionAppSyncFunction6BE14593                         AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:07 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS MutationupdateTodoinit0FunctionMutationupdateTodoinit0FunctionAppSyncFunction1B95BB19                     AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:07 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS MutationupdateTodopostAuth0FunctionMutationupdateTodopostAuth0FunctionAppSyncFunction50C507D7             AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:07 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS QuerylistTodospostAuth0FunctionQuerylistTodospostAuth0FunctionAppSyncFunction154D8577                     AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:07 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS SubscriptionOnDeleteTodoDataResolverFnSubscriptionOnDeleteTodoDataResolverFnAppSyncFunction3E641E8C       AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:07 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS MutationcreateTodopostAuth0FunctionMutationcreateTodopostAuth0FunctionAppSyncFunctionED59EB9F             AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:07 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS SubscriptiononDeleteTodopostAuth0FunctionSubscriptiononDeleteTodopostAuth0FunctionAppSyncFunctionE131CBE7 AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:07 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS SubscriptiononUpdateTodopostAuth0FunctionSubscriptiononUpdateTodopostAuth0FunctionAppSyncFunction04445BC7 AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:08 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS MutationdeleteTodopostAuth0FunctionMutationdeleteTodopostAuth0FunctionAppSyncFunction483271A2             AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:08 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS TodoTable                                                                                                 AWS::DynamoDB::Table
      Wed Dec 01 2021 16:41:08 GMT-0800 (Pacific Standard Time) Resource creation Initiated
CREATE_IN_PROGRESS TodoIAMRole2DA8E66E                                                                                       AWS::IAM::Role
      Wed Dec 01 2021 16:41:08 GMT-0800 (Pacific Standard Time) Resource creation Initiated
- Updating resources in the cloud. This may take a few minutes...

CREATE_IN_PROGRESS SubscriptiononCreateTodopostAuth0FunctionSubscriptiononCreateTodopostAuth0FunctionAppSyncFunction18E34C4E AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:09 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS MutationcreateTodoinit0FunctionMutationcreateTodoinit0FunctionAppSyncFunction54DE5B8B                     AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:09 GMT-0800 (Pacific Standard Time) Resource creation Initiated
CREATE_IN_PROGRESS SubscriptionOnUpdateTodoDataResolverFnSubscriptionOnUpdateTodoDataResolverFnAppSyncFunction523DF0E4       AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:09 GMT-0800 (Pacific Standard Time) Resource creation Initiated
CREATE_IN_PROGRESS SubscriptiononDeleteTodopostAuth0FunctionSubscriptiononDeleteTodopostAuth0FunctionAppSyncFunctionE131CBE7 AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:09 GMT-0800 (Pacific Standard Time) Resource creation Initiated
CREATE_COMPLETE    SubscriptionOnUpdateTodoDataResolverFnSubscriptionOnUpdateTodoDataResolverFnAppSyncFunction523DF0E4       AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:09 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS QuerylistTodospostAuth0FunctionQuerylistTodospostAuth0FunctionAppSyncFunction154D8577                     AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:09 GMT-0800 (Pacific Standard Time) Resource creation Initiated
CREATE_COMPLETE    MutationcreateTodoinit0FunctionMutationcreateTodoinit0FunctionAppSyncFunction54DE5B8B                     AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:09 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS MutationupdateTodopostAuth0FunctionMutationupdateTodopostAuth0FunctionAppSyncFunction50C507D7             AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:09 GMT-0800 (Pacific Standard Time) Resource creation Initiated
CREATE_COMPLETE    SubscriptiononDeleteTodopostAuth0FunctionSubscriptiononDeleteTodopostAuth0FunctionAppSyncFunctionE131CBE7 AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:09 GMT-0800 (Pacific Standard Time)
CREATE_COMPLETE    QuerylistTodospostAuth0FunctionQuerylistTodospostAuth0FunctionAppSyncFunction154D8577                     AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:09 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS QuerygetTodopostAuth0FunctionQuerygetTodopostAuth0FunctionAppSyncFunction6BE14593                         AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:09 GMT-0800 (Pacific Standard Time) Resource creation Initiated
CREATE_COMPLETE    MutationupdateTodopostAuth0FunctionMutationupdateTodopostAuth0FunctionAppSyncFunction50C507D7             AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:10 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS SubscriptionOnCreateTodoDataResolverFnSubscriptionOnCreateTodoDataResolverFnAppSyncFunction462A70C9       AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:10 GMT-0800 (Pacific Standard Time) Resource creation Initiated
CREATE_COMPLETE    QuerygetTodopostAuth0FunctionQuerygetTodopostAuth0FunctionAppSyncFunction6BE14593                         AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:10 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS SubscriptionOnDeleteTodoDataResolverFnSubscriptionOnDeleteTodoDataResolverFnAppSyncFunction3E641E8C       AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:10 GMT-0800 (Pacific Standard Time) Resource creation Initiated
CREATE_COMPLETE    SubscriptionOnCreateTodoDataResolverFnSubscriptionOnCreateTodoDataResolverFnAppSyncFunction462A70C9       AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:10 GMT-0800 (Pacific Standard Time)
CREATE_COMPLETE    SubscriptionOnDeleteTodoDataResolverFnSubscriptionOnDeleteTodoDataResolverFnAppSyncFunction3E641E8C       AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:10 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS SubscriptiononUpdateTodopostAuth0FunctionSubscriptiononUpdateTodopostAuth0FunctionAppSyncFunction04445BC7 AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:10 GMT-0800 (Pacific Standard Time) Resource creation Initiated
CREATE_IN_PROGRESS MutationdeleteTodopostAuth0FunctionMutationdeleteTodopostAuth0FunctionAppSyncFunction483271A2             AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:10 GMT-0800 (Pacific Standard Time) Resource creation Initiated
CREATE_COMPLETE    SubscriptiononUpdateTodopostAuth0FunctionSubscriptiononUpdateTodopostAuth0FunctionAppSyncFunction04445BC7 AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:10 GMT-0800 (Pacific Standard Time)
CREATE_COMPLETE    MutationdeleteTodopostAuth0FunctionMutationdeleteTodopostAuth0FunctionAppSyncFunction483271A2             AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:10 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS MutationupdateTodoinit0FunctionMutationupdateTodoinit0FunctionAppSyncFunction1B95BB19                     AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:11 GMT-0800 (Pacific Standard Time) Resource creation Initiated
CREATE_IN_PROGRESS MutationcreateTodopostAuth0FunctionMutationcreateTodopostAuth0FunctionAppSyncFunctionED59EB9F             AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:11 GMT-0800 (Pacific Standard Time) Resource creation Initiated
CREATE_COMPLETE    MutationupdateTodoinit0FunctionMutationupdateTodoinit0FunctionAppSyncFunction1B95BB19                     AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:11 GMT-0800 (Pacific Standard Time)
CREATE_COMPLETE    MutationcreateTodopostAuth0FunctionMutationcreateTodopostAuth0FunctionAppSyncFunctionED59EB9F             AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:11 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS SubscriptiononCreateTodopostAuth0FunctionSubscriptiononCreateTodopostAuth0FunctionAppSyncFunction18E34C4E AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:11 GMT-0800 (Pacific Standard Time) Resource creation Initiated
CREATE_COMPLETE    SubscriptiononCreateTodopostAuth0FunctionSubscriptiononCreateTodopostAuth0FunctionAppSyncFunction18E34C4E AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:11 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS SubscriptiononDeleteTodoResolver                                                                          AWS::AppSync::Resolver        
      Wed Dec 01 2021 16:41:13 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS SubscriptiononUpdateTodoResolver                                                                          AWS::AppSync::Resolver        
      Wed Dec 01 2021 16:41:13 GMT-0800 (Pacific Standard Time)
| Updating resources in the cloud. This may take a few minutes...

CREATE_IN_PROGRESS SubscriptiononCreateTodoResolver AWS::AppSync::Resolver Wed Dec 01 2021 16:41:14 GMT-0800 (Pacific Standard Time) 
- Updating resources in the cloud. This may take a few minutes...

CREATE_IN_PROGRESS SubscriptiononDeleteTodoResolver AWS::AppSync::Resolver Wed Dec 01 2021 16:41:15 GMT-0800 (Pacific Standard Time) Resource creation Initiated
CREATE_COMPLETE    SubscriptiononDeleteTodoResolver AWS::AppSync::Resolver Wed Dec 01 2021 16:41:15 GMT-0800 (Pacific Standard Time)

CREATE_IN_PROGRESS SubscriptiononUpdateTodoResolver AWS::AppSync::Resolver Wed Dec 01 2021 16:41:16 GMT-0800 (Pacific Standard Time) Resource creation Initiated
CREATE_IN_PROGRESS SubscriptiononCreateTodoResolver AWS::AppSync::Resolver Wed Dec 01 2021 16:41:16 GMT-0800 (Pacific Standard Time) Resource creation Initiated
CREATE_COMPLETE    SubscriptiononCreateTodoResolver AWS::AppSync::Resolver Wed Dec 01 2021 16:41:16 GMT-0800 (Pacific Standard Time)

CREATE_COMPLETE    SubscriptiononUpdateTodoResolver AWS::AppSync::Resolver Wed Dec 01 2021 16:41:16 GMT-0800 (Pacific Standard Time)

- Updating resources in the cloud. This may take a few minutes...

CREATE_COMPLETE TodoIAMRole2DA8E66E AWS::IAM::Role Wed Dec 01 2021 16:41:22 GMT-0800 (Pacific Standard Time) 
- Updating resources in the cloud. This may take a few minutes...

CREATE_IN_PROGRESS DynamoDBAccess71ABE5AE AWS::IAM::Policy Wed Dec 01 2021 16:41:25 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS DynamoDBAccess71ABE5AE AWS::IAM::Policy Wed Dec 01 2021 16:41:26 GMT-0800 (Pacific Standard Time) Resource creation Initiated
/ Updating resources in the cloud. This may take a few minutes...

CREATE_COMPLETE    DynamoDBAccess71ABE5AE           AWS::IAM::Policy         Wed Dec 01 2021 16:41:39 GMT-0800 (Pacific Standard Time)

CREATE_COMPLETE    TodoTable                        AWS::DynamoDB::Table     Wed Dec 01 2021 16:41:40 GMT-0800 (Pacific Standard Time)

CREATE_IN_PROGRESS TodoIAMRoleDefaultPolicy7BBBF45B AWS::IAM::Policy         Wed Dec 01 2021 16:41:42 GMT-0800 (Pacific Standard Time)

CREATE_IN_PROGRESS TodoDataSource                   AWS::AppSync::DataSource Wed Dec 01 2021 16:41:42 GMT-0800 (Pacific Standard Time)

CREATE_IN_PROGRESS TodoIAMRoleDefaultPolicy7BBBF45B AWS::IAM::Policy         Wed Dec 01 2021 16:41:43 GMT-0800 (Pacific Standard Time) Resource creation Initiated
\ Updating resources in the cloud. This may take a few minutes...

CREATE_IN_PROGRESS TodoDataSource                                                                          AWS::AppSync::DataSource            Wed Dec 01 2021 16:41:44 GMT-0800 (Pacific Standard Time) Resource creation Initiated
CREATE_COMPLETE    TodoDataSource                                                                          AWS::AppSync::DataSource            Wed Dec 01 2021 16:41:44 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS QueryGetTodoDataResolverFnQueryGetTodoDataResolverFnAppSyncFunctionE2B57DAD             AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:47 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS MutationDeleteTodoDataResolverFnMutationDeleteTodoDataResolverFnAppSyncFunction3879153F AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:47 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS MutationUpdateTodoDataResolverFnMutationUpdateTodoDataResolverFnAppSyncFunctionBC238C49 AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:47 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS MutationCreateTodoDataResolverFnMutationCreateTodoDataResolverFnAppSyncFunction900EC5CF AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:47 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS QueryListTodosDataResolverFnQueryListTodosDataResolverFnAppSyncFunctionF825FE47         AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:48 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS MutationUpdateTodoDataResolverFnMutationUpdateTodoDataResolverFnAppSyncFunctionBC238C49 AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:48 GMT-0800 (Pacific Standard Time) Resource creation Initiated
CREATE_COMPLETE    MutationUpdateTodoDataResolverFnMutationUpdateTodoDataResolverFnAppSyncFunctionBC238C49 AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:49 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS MutationDeleteTodoDataResolverFnMutationDeleteTodoDataResolverFnAppSyncFunction3879153F AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:49 GMT-0800 (Pacific Standard Time) Resource creation Initiated
CREATE_IN_PROGRESS MutationCreateTodoDataResolverFnMutationCreateTodoDataResolverFnAppSyncFunction900EC5CF AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:49 GMT-0800 (Pacific Standard Time) Resource creation Initiated
- Updating resources in the cloud. This may take a few minutes...

CREATE_COMPLETE    MutationDeleteTodoDataResolverFnMutationDeleteTodoDataResolverFnAppSyncFunction3879153F AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:49 GMT-0800 (Pacific Standard Time)
CREATE_COMPLETE    MutationCreateTodoDataResolverFnMutationCreateTodoDataResolverFnAppSyncFunction900EC5CF AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:49 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS QueryGetTodoDataResolverFnQueryGetTodoDataResolverFnAppSyncFunctionE2B57DAD             AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:50 GMT-0800 (Pacific Standard Time) Resource creation Initiated
CREATE_IN_PROGRESS QueryListTodosDataResolverFnQueryListTodosDataResolverFnAppSyncFunctionF825FE47         AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:50 GMT-0800 (Pacific Standard Time) Resource creation Initiated
CREATE_COMPLETE    QueryGetTodoDataResolverFnQueryGetTodoDataResolverFnAppSyncFunctionE2B57DAD             AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:50 GMT-0800 (Pacific Standard Time)
CREATE_COMPLETE    QueryListTodosDataResolverFnQueryListTodosDataResolverFnAppSyncFunctionF825FE47         AWS::AppSync::FunctionConfiguration Wed Dec 01 2021 16:41:50 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS DeleteTodoResolver                                                                      AWS::AppSync::Resolver              Wed Dec 01 2021 16:41:52 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS CreateTodoResolver                                                                      AWS::AppSync::Resolver              Wed Dec 01 2021 16:41:52 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS UpdateTodoResolver                                                                      AWS::AppSync::Resolver              Wed Dec 01 2021 16:41:52 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS GetTodoResolver                                                                         AWS::AppSync::Resolver              Wed Dec 01 2021 16:41:53 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS ListTodoResolver                                                                        AWS::AppSync::Resolver              Wed Dec 01 2021 16:41:53 GMT-0800 (Pacific Standard Time)
\ Updating resources in the cloud. This may take a few minutes...

CREATE_IN_PROGRESS DeleteTodoResolver AWS::AppSync::Resolver Wed Dec 01 2021 16:41:54 GMT-0800 (Pacific Standard Time) Resource creation Initiated
CREATE_COMPLETE    DeleteTodoResolver AWS::AppSync::Resolver Wed Dec 01 2021 16:41:54 GMT-0800 (Pacific Standard Time)
- Updating resources in the cloud. This may take a few minutes...

CREATE_IN_PROGRESS UpdateTodoResolver               AWS::AppSync::Resolver Wed Dec 01 2021 16:41:54 GMT-0800 (Pacific Standard Time) Resource creation Initiated
CREATE_IN_PROGRESS CreateTodoResolver               AWS::AppSync::Resolver Wed Dec 01 2021 16:41:54 GMT-0800 (Pacific Standard Time) Resource creation Initiated
CREATE_COMPLETE    CreateTodoResolver               AWS::AppSync::Resolver Wed Dec 01 2021 16:41:54 GMT-0800 (Pacific Standard Time)

CREATE_COMPLETE    UpdateTodoResolver               AWS::AppSync::Resolver Wed Dec 01 2021 16:41:54 GMT-0800 (Pacific Standard Time)

CREATE_IN_PROGRESS GetTodoResolver                  AWS::AppSync::Resolver Wed Dec 01 2021 16:41:54 GMT-0800 (Pacific Standard Time) Resource creation Initiated
CREATE_COMPLETE    GetTodoResolver                  AWS::AppSync::Resolver Wed Dec 01 2021 16:41:55 GMT-0800 (Pacific Standard Time)

CREATE_COMPLETE    TodoIAMRoleDefaultPolicy7BBBF45B AWS::IAM::Policy       Wed Dec 01 2021 16:41:56 GMT-0800 (Pacific Standard Time)

- Updating resources in the cloud. This may take a few minutes...

CREATE_IN_PROGRESS ListTodoResolver AWS::AppSync::Resolver Wed Dec 01 2021 16:42:01 GMT-0800 (Pacific Standard Time) Resource creation Initiated
CREATE_COMPLETE    ListTodoResolver AWS::AppSync::Resolver Wed Dec 01 2021 16:42:01 GMT-0800 (Pacific Standard Time)
\ Updating resources in the cloud. This may take a few minutes...

CREATE_COMPLETE amplify-reactamplified-dev-162717-apireactamplified-L8DTJHF2K7KE-Todo-1FEC0XL5N2MR9 AWS::CloudFormation::Stack Wed Dec 01 2021 16:42:04 GMT-0800 (Pacific Standard Time) 
| Updating resources in the cloud. This may take a few minutes...

CREATE_COMPLETE Todo AWS::CloudFormation::Stack Wed Dec 01 2021 16:42:18 GMT-0800 (Pacific Standard Time) 
| Updating resources in the cloud. This may take a few minutes...

CREATE_IN_PROGRESS CustomResourcesjson AWS::CloudFormation::Stack Wed Dec 01 2021 16:42:20 GMT-0800 (Pacific Standard Time)
CREATE_IN_PROGRESS CustomResourcesjson AWS::CloudFormation::Stack Wed Dec 01 2021 16:42:21 GMT-0800 (Pacific Standard Time) Resource creation Initiated    
/ Updating resources in the cloud. This may take a few minutes...

CREATE_IN_PROGRESS amplify-reactamplified-dev-162717-apireactamplified-L8DTJHF2K7KE-CustomResourcesjson-1CAGKQHF8NZ2A AWS::CloudFormation::Stack Wed Dec 01 2021 16:42:21 GMT-0800 (Pacific Standard Time) User Initiated
/ Updating resources in the cloud. This may take a few minutes...

CREATE_COMPLETE amplify-reactamplified-dev-162717-apireactamplified-L8DTJHF2K7KE-CustomResourcesjson-1CAGKQHF8NZ2A AWS::CloudFormation::Stack Wed Dec 01 2021 16:42:25 GMT-0800 (Pacific Standard Time) 
| Updating resources in the cloud. This may take a few minutes...

CREATE_COMPLETE CustomResourcesjson AWS::CloudFormation::Stack Wed Dec 01 2021 16:42:32 GMT-0800 (Pacific Standard Time)
\ Updating resources in the cloud. This may take a few minutes...

CREATE_COMPLETE amplify-reactamplified-dev-162717-apireactamplified-L8DTJHF2K7KE AWS::CloudFormation::Stack Wed Dec 01 2021 16:42:34 GMT-0800 (Pacific Standard Time) 
- Updating resources in the cloud. This may take a few minutes...

CREATE_COMPLETE apireactamplified AWS::CloudFormation::Stack Wed Dec 01 2021 16:42:52 GMT-0800 (Pacific Standard Time) 
- Updating resources in the cloud. This may take a few minutes...

UPDATE_COMPLETE_CLEANUP_IN_PROGRESS amplify-reactamplified-dev-162717 AWS::CloudFormation::Stack Wed Dec 01 2021 16:42:55 GMT-0800 (Pacific Standard Time) 
UPDATE_COMPLETE                     amplify-reactamplified-dev-162717 AWS::CloudFormation::Stack Wed Dec 01 2021 16:42:55 GMT-0800 (Pacific Standard Time) 
√ Generated GraphQL operations successfully and saved at src\graphql
√ All resources are updated in the cloud

GraphQL endpoint: https://lvi4kbpj6zcobhr2rarchbevoa.appsync-api.us-west-1.amazonaws.com/graphql
GraphQL API KEY: da2-b3x62eazy5bhxczvmbhgvspwny


$ amplify status

    Current Environment: dev

┌──────────┬────────────────┬───────────┬───────────────────┐
│ Category │ Resource name  │ Operation │ Provider plugin   │
├──────────┼────────────────┼───────────┼───────────────────┤
│ Api      │ reactamplified │ No Change │ awscloudformation │
└──────────┴────────────────┴───────────┴───────────────────┘

GraphQL endpoint: https://lvi4kbpj6zcobhr2rarchbevoa.appsync-api.us-west-1.amazonaws.com/graphql
GraphQL API KEY: da2-b3x62eazy5bhxczvmbhgvspwny
```
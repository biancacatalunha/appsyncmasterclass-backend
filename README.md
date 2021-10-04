# appsyncmasterclass-backend
Backend for the AppSync masterclass demo app

# Scripts
initialize package.json
npm init -y

install the serverless framework on this project, non breaking version
npm i --save-dev serverless@2.4.0

create a serverless project
npm run sls -- create -t aws-nodejs

allows to have a custom appsync session in serverless.appsync-api.yml
npm i --save-dev serverless-appsync-plugin


# Notes 
AppSync is a fully managed GraphQl service, responsible for mapping requests to different resolvers.
Supported:
- HTTP/REST
- DynamoDB
- RDS(Aurora Serveless)
- Elastic Search
- Lambda

Go from AppSync straight to the DB.

Dynamo DB Semi schema - Only needs to define the primary key, the rest is defined per item
CloufFormation Infrastructure as code. 
Template: JSON/Yaml file, blueprint
Stack: Created based on the template
Cognito 
User Pools: Registration, Verify email/phone, segure sign-in, forgotten password, change password, sign-out (Encrypt data server-side, token based auth, CATPCHA, user groups) 
Identity pools: Authentic providers like Google and Facebook
Sync: Sync user profile data across multiple devices

Pro tips:  (chap. 4, video 5)
1. Avoid local simulation (e.g LocalStack),they’re more work than is worth it, and hides common failure modes such as misconfigured permissions and resources policies
2. In serverless applications it is better to write integration tests
3. Only use mocks for AWS services to simulate hard-to-reproduce failure cases
4. But always mock your own APIs during integration testing - they are not as stable as AWS services
5. Use temporary stacks to run e2e tests
https://theburningmonk.com/2019/09/why-you-should-use-temporary-stacks-when-you-do-serverless/

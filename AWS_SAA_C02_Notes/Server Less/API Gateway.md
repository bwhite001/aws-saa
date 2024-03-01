Clients can access [[Lambda]] using API gateway
web socket protocol
versioning
support dev, test environments
Authentication and authorisation
Swagger/ Open API to define APIs
validation and transform
Generate SDK and API specs
Caching

*Endpoint types*

1. Edge-Optimized
2. Regional
3. Private


*Security*

1. [[IAM]] - Sig v4 capability adding authentication  info to AWS API requests. Cant be used by people outside of the organization
2. Lambda Authorizer/ Custom Authorizer - lambda to validate the token in header. Used with OAth/ SAML
3. Congnito User Pools - fully managed by aws. Manages authentication not authorization, email, password, MFA, password polices, can enable Federated Indenties from Google , facebook, SAML ... sends back a JWT


Congnito Identity Pools - Federated Identity, provide AWS credentials to users so they can access AWS resources directly. For App users

Cognito Sync - Sync data from device to cognito. Replaced by AppSync. to store state of an app.

*Serverless Application Model* - SAM
Framework for serverless apps
YAML configs
can run Lambda, API gateway and Dynamo db locally
can use CodeDeploy to deploy [[Lambda]] functions
lets users outside AWS to assume temp role for accessing AWS resources
No need to create [[IAM]] users

*SAML 2.0*
Activity Directory / ADFS
access to AWS Console or CLI
uses STS API AssumeRoleWithSAML
Amazon Single Sign On - [[SSO]] is the new simpler way

*Custom Identity Broker App*
when not compatible with SAML 2.0
identity broker must determine  the appropriate IAM policy
STS Api AssumeRole or GetFederationToken
Note recommended by AWS. Use Cognito

*Cognito*

Provide direct acces to AWS resoures from the Client Side

*Active Directory*

1. AWS Managed AD
	1. manage users locally, MFA
2. AD Connector- proxy
	1. proxy to redirect to on premise AD
	2. Users are managed on the on premise AD
3. Simple AD
	1.  AD compatible managed directory on AWS
	2.  Cannot be joined with on-premise AD
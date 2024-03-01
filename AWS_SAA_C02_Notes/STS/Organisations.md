Global Service
manage multiple AWS accounts
master/management and member accounts. MAster accounts cant be changed while member accounts can
member account must be part of one organization
Member accounts can be transferred from one organization to another
Consolidated billing across all accounts - billing payment methods

Strategies -  account per department/cost center/dev,test etc
can establish cross account roles for admin purpose

Organizational Units - OU- groups accounts
root OU covers everything including master account

Service Control Policies (SCP) - whitelist or blacklist [[IAM]] actions, Applied at the OU or at the Account level, Does not apply to master account, SCP is applied to User and Roles of the account including root, SCP does not affect service linked roles, SCP must have an explicit Allow(does not allow anything by default)
eg: Restrict access to certain services

while migrating master accounts all sub accounts are also migrated.

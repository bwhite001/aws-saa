User are people within an organization
Root user is created by default.
Users can be added to [[Group]]s.
A user can belong to multiple [[Group]].
A user doesn't have to belong to a [[Group]].

[[User]]s and [[Group]]s can avail permissions based on a construct called [[Policy]]

User can be root user or IAM user. Root user can create IAM users
AWS Account ID and Alias belongs to all the users (Including ROOT user) in the account.
The AWS Account ID and Alias belongs to all the users in the account, including the root user. This means that you can use the same account ID or alias to sign in to the AWS Management Console for all IAM users. However, it is best practice to use a different alias for each IAM user. This makes it easier to track who is using the account and what resources they have access to.

[[Security Group]] needs to be configured for ssh access
22 is the default port
ec2-user is the default user
will need a [[Key Pair.pem]] file for access
ssh -i KeyPair.pem ec2-user@ec2publicip

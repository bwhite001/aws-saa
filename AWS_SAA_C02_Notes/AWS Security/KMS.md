AWS manages the key
integrated with [[IAM]]

*Custom Master Key Types*
1. Symmetric (AES-256)- used for [[envelop encryption]], user never see the key unencrypted
2. Asymmetric (RSA and ECC key pairs) -  Used for Sign/Verify operations. used by users outside AWS who can't call KMS API
key usage can be tracked by [[Cloud Trail]]

can only encrypt upto 4KB of DATA per call
if size > 4KB use [[envelop encryption]]

Keys are bound to [[Region]]

KMS Key Policy - policy for the key

Automatic Key Rotation - 1 year, previous key is kept, same CMK id
Manual Key Rotation - different CMK id, previous key is kept

[[SSM Parameters]]
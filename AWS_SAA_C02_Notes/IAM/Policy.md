[[User]]s and [[Group]]s can avail permissions based on a construct called [[Policy]]
Example

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "directconnect:Describe*",
                "directconnect:List*",
                "ec2:DescribeVpnGateways",
                "ec2:DescribeTransitGateways"
            ],
            "Resource": "*"
        }
    ]
}

```

Inline policy - Policy attached to a [[User]].

Inheritance will be applied when there are Policies applied to a  [[Group]] and a [[User]] belong to  many [[Group]]s.

We can use IAM POlicy simulator to test
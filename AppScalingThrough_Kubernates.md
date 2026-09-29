1. Create S3 Bucket which will hold all the Vedios.
<img width="1896" height="862" alt="image" src="https://github.com/user-attachments/assets/67b55125-c4bc-4194-b65b-9d0165f5eb9d" />
<img width="1917" height="822" alt="image" src="https://github.com/user-attachments/assets/5dfb34c6-61b9-4c67-a76d-4138d987bb97" />

2. Create a IAM Role which will be responsibe for having only Readonly access for the specific S3 Bucket.
<img width="1906" height="862" alt="image" src="https://github.com/user-attachments/assets/9d120476-96a1-4f21-a406-aabe13c19b99" />

## 🔐 IAM Role Permissions
Note : Replace #S3-Bucket# with the Specific Bucket Name if having multiple Buckets then in the same Resoure section add other in comma seperated format.

```json
{
	"Version": "2012-10-17",
	"Statement": [
		{
			"Sid": "S3FilesPermissions",
			"Effect": "Allow",
			"Action": [
				"s3files:Get*",
				"s3files:List*"
			],
			"Resource": [
				"#S3-Bucket#"
			]
		},
		{
			"Sid": "EC2ReadOnlyPermissions",
			"Effect": "Allow",
			"Action": [
				"ec2:DescribeSubnets",
				"ec2:DescribeNetworkInterfaces",
				"ec2:DescribeNetworkInterfaceAttribute",
				"ec2:DescribeSecurityGroups",
				"ec2:DescribeVpcs",
				"ec2:DescribeAvailabilityZones"
			],
			"Resource": "*"
		}
	]
}

```
4.  Create new User who will have Readonly Access for StreaingApp S3 Bucket.
<img width="1906" height="865" alt="image" src="https://github.com/user-attachments/assets/af179327-dbc9-4a39-90b7-0ebc9c30be99" />

5. 

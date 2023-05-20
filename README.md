# **How to READ-only access IAm user to one speceifc S3 bucket**
---
## _create s3 bucket_
* give the name one specefic name for s3 bucket it will not take already exists bucketname.
* trun off all block-access in your bucket.
* ALCs enabled our bucket and create bucket.
* create folder inside the bucket and inside the bucket upload ojects.
---

## _create IAM USER_
* create one iam user and give username and custom password.
* if you want access-key seceret-key then you create that.

## _create custom policy_
* click the button create policy

```python

{
        "Version": "2012-10-17",
        "Statement": [
                {
                        "Sid": "S3BucketAccess",
                        "Effect": "Allow",
                        "Action": [
                                "s3:ListAllMyBuckets",
                                "s3:GetBucketLocation"
                        ],
                        "Resource": "*"
                },
                {
                        "Sid": "S3ObjectAccess",
                        "Effect": "Allow",
                        "Action": [
                                "s3:GetObject"
                        ],
                        "Resource": "arn:aws:s3:::<bucket-name>/<object-name>/*"
                }
        ]
}
```
* use that policy create custom policy
* attach this policy to what we craeted user
* logout our root access


 


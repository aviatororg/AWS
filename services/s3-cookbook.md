# Cook

### Setup Cross Account Permissions
- description: access an s3 bucket from another account
- docs: http://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html
- legend
    - account A: account with s3 bucket that we will be enabling cross account permissions on
    - account B: account that will access bucket in account A

- steps
    - in account A, setup cross account bucket policy in the bucket that account B will be given access to
```
{
   "Version": "2012-10-17",
   "Statement": [
      {
         "Sid": "Example permissions",
         "Effect": "Allow",
         "Principal": {
            "AWS": "arn:aws:iam::{AccountB-ID}:root"
         },
         "Action": [
            "s3:GetBucketLocation",
            "s3:ListBucket"
         ],
         "Resource": [
            "arn:aws:s3:::{BUCKET_NAME}"
         ]
      }
   ]
}
```

### Perform a multi-part upload
- req: [jq](https://stedolan.github.io/jq/)

- steps
    - setup config
    ```
    bucket={BUCKET_NAME|eg: mybucket}
    folder={BUCKET_KEY|eg: assets}
    path_to_target={PATH_TARGET|eg: /foo/bar/data}
    path_to_staging={PATH_TO_STAGING|eg: /tmp/}
    target={TARGET|eg: foo.tgz}
    multipart_upload_metadata_file=s3_metadata

    profile={AWS_PROFILE}

    region={AWS_REGION}

    upload_id=$(aws --profile $profile --region $region s3api create-multipart-upload --bucket $bucket --key $folder/$target | jq -r '.["UploadId"] ')
    ```
    - execute multipart upload

# Related
- [Home Page](https://aws.amazon.com/s3/)
- [Developer Guide](https://docs.aws.amazon.com/AmazonS3/latest/dev/Welcome.html)
- [FAQ](https://aws.amazon.com/s3/faqs/)
- [Pricing](https://aws.amazon.com/s3/pricing/)

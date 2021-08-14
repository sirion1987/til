# Get s3 bucket list

```
$ aws \
    s3api \
    list-buckets \
    --query "Buckets[].Name"
```

# Show s3 metrics

```
$ aws \
    cloudwatch \
    get-metric-statistics \
    --metric-name BucketSizeBytes \
    --namespace AWS/S3 \
    --start-time 2019-10-19T00:00:00Z \
    --end-time 2019-12-12T00:00:00Z \
    --statistics Average \
    --unit Bytes \
    --region eu-west-1 \
    --dimensions \
        Name=BucketName,Value=<bucketName> \
        Name=StorageType,Value=StandardStorage \
    --period 86400 \
    --output json
```

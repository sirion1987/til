# Sync buckets

```
aws s3 sync s3://<FROM_BUCKET> s3://<TO_BUCKET> --acl <ACL_POLICY>
```

## ACL Policy

* private
* public-read
* public-read-write
* authenticated-read
* aws-exec-read,
* bucket-owner-read
* bucket-owner-full-control
* log-delivery-write

# Copy S3 objects from another AWS account

* [Doc](https://aws.amazon.com/it/premiumsupport/knowledge-center/copy-s3-objects-account/)

## References

1. [Aws Docs](https://docs.aws.amazon.com/cli/latest/reference/s3/sync.html#examples)

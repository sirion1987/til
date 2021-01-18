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

## References

1. [Aws Docs](https://docs.aws.amazon.com/cli/latest/reference/s3/sync.html#examples)

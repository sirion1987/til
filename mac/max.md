# Extended attributes

```
$ ls -@al
-rw-r--r--@  1 user  staff   80995  1 Gen 00:00 file.png
        com.apple.quarantine      ...

```

## Remove extende attribute

```
$ xattr -d com.apple.quarantine file.png
```

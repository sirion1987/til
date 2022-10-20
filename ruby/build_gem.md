# Create a new Gem with bundle

```
$ gem bundle <gem_name>
```

# Build the Gem

```
$ gem build <gem_name>.gemspec
```

# Local test with irb

```
$ gem install <builded_gem>.gem
$ irb
> require '<gem_name>'
```

# Publish the Gem

```
$ gem push <builded_gem>.gem
```

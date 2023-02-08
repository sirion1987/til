## zsh configuration (MacOS)

``` 
# ~/.zshrc

. $(brew --prefix asdf)/libexec/asdf.sh

...
plugins=(
  asdf
  ...
)
...
```

## Update plugin list

```
$ asdf plugin-update <plugin_name>
```

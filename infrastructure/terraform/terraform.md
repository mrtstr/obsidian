- commands will only directly use the configuration files in one directory, which is usually the current working directory

```
terraform -chdir="./path-to-dir" apply
```

```
terraform apply [options] ./path-to-dir
```
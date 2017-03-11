Centos warning: setlocale: LC_CTYPE: cannot change locale (UTF-8): No such file or directory

```shell
vi /etc/environment
```

add these lines...
```shell
LANG=en_US.utf-8
LC_ALL=en_US.utf-8
```
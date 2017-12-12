How to set the hostname of a Mac OS X workstation from the terminal.

Mac Primary hostname
```shell
sudo scutil --set HostName <new host name>
```

Mac Bonjour hostname
```shell
sudo scutil --set LocalHostName <new host name>
```

Mac Computer name
```shell
sudo scutil --set ComputerName <new name>
```

Flush DNS cache
```shell
dscacheutil -flushcache
```
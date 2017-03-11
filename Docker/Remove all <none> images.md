Remove all <none> images
```shell
docker rmi $(docker images -a | grep "^<none>" | awk '{print $3}')
```
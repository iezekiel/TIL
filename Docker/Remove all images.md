*Warning:* This will destroy all your images. It will not be possible to restore them!
```shell
docker rmi $(docker images -q)
```
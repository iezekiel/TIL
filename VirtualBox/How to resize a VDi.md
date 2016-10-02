VirtualBox does not have a GUI option to resize your virtual disk, it can
be done throught the command line tools installed.

1. Shutdown virutal machine.
2. Go to 
```shell
cd /Applications/VirtualBox.app/Contents/Resources/VirtualBoxVM.app/Contents/MacOS/
```
3. Run the resize command replacing [new size in MB]
```shell
VBoxManage modifyhd --resize [new size in MB] [/path/to/vdi]
```
# Installation

## Ubuntu Swap
```
$ free
$ sudo gedit /etc/sysctl.conf
#################################################
# Set Swap usable availability
#        Swap <-------> physical memory
# default: 60%                40%
vm.swappiness=20
```
## Mount Drives without logo

## Install Nvidia Driver, cuda, cuDnn, Anaconda, Tensorflow  
Nvidia Driver can be installed by CUDA (Some times doesn't work)  
* In this condiction, When "X server is running"  
```
$ sudo service lightdm stop
$ rm /tmp X*-lock
```
* Independent install Nvidia Driver, follow [this](https://gist.github.com/wangruohui/df039f0dc434d6486f5d4d098aa52d07)  

`ATTENTION`      
* If you can not solve the nouveau problem, try -no-x-check -no-nouveau-check, the check is not necessary, in [this](https://blog.csdn.net/wangsidadehao/article/details/70255754)  

multiple CUDA    
```
$ cd /usr/local   #cuda is a soft link
$ stat cuda

File: 'cuda' -> '/usr/local/cuda-9.0'
  Size: 19        	Blocks: 0          IO Block: 4096   symbolic link
Device: 801h/2049d	Inode: 15337567    Links: 1
Access: (0777/lrwxrwxrwx)  Uid: (    0/    root)   Gid: (    0/    root)
Access: 2018-12-27 22:38:59.461332996 +0900
Modify: 2018-12-27 22:38:51.621298141 +0900
Change: 2018-12-27 22:38:51.621298141 +0900
 Birth: -
```  
cuDNN  
```
$ sudo cp cuda/include/cudnn.h /usr/local/cuda/include
$ sudo cp cuda/lib64/libcudnn* /usr/local/cuda/lib64
$ sudo chmod a+r /usr/local/cuda/include/cudnn.h /usr/local/cuda/lib64/libcudnn*
```

## openCV with videoCapture
```
$ conda install -c anaconda opencv
```


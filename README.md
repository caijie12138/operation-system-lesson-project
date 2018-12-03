### READ ME
###（a）安装bochs
Mac系统上安装bochs请参考

http://blog.csdn.net/yzr1183739890/article/details/54864841

Linux上安装请参考

（安装过程会碰到很多的错误，但是百度都能解决）

http://os.51cto.com/art/201407/446838_all.htm

###（b）运行
####bochs 2.6.9

进入"支持保护模式的简单操作系统的设计与实现\_14221091\_蔡杰"文件夹内，直接执行

bochs -f bochsrc.bxrc

####bochs 2.4

需要修改配置文件bochsrc.bxrc如下：

\# how much memory the emulated machine will have
megs: 32

\# filename of ROM images
romimage: file=$BXSHARE/BIOS-bochs-latest
vgaromimage: file=$BXSHARE/VGABIOS-lgpl-latest

\# what disk images will be used 
floppya: 1_44=TINIX.IMG, status=inserted

\# choose the boot disk.
boot: a

\# where do we send log messages?
log: bochsout.txt

\# disable the mouse, since Tinix is text only
mouse: enabled=0

\# enable key mapping, using US layout as default.
keyboard_mapping: enabled=0, map=$BXSHARE/keymaps/x11-pc-us.map

之后再执行：

bochs -f bochsrc.bxrc

即可。

###（c）修改
####以下操作在"源程序"文件夹下修改：

如果添加新文件需要修改MakeFile文件

暂时支持在Linux上修改

在terminal中依次执行以下指令即可：

make clean

make 

make buildimg


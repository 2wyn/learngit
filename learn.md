# 学习笔记

## 第四章

* 为了避免瞬间断电造成的Linux系统危害，建议做为服务器的Linux主机应该加上不断电系统来持续提供稳定的电力
* 不要使用 root 直接登陆系统，应使用一般帐号登陆系统，有需要再转换身份
* 在X的环境下想要“强制”重新启动X的组合按键为：“[alt]+[ctrl]+[backspace]”
*  默认情况下，Linux提供tty1~tty6的终端机界面
*  在终端机环境中，可依据提示字符为$或#判断为一般帐号或root帐号
*  取得终端机支持的语系数据可下达“echo $LANG”或“locale”指令 
* date可显示日期、cal可显示日历、bc可以做为计算机软件

## 第五章

* 利用ls -l显示的文件属性中，第一个字段是文件的权限，共有十个位，第一个位是文件类型， 

  接下来三个为一组共三组，为使用者、群组、其他人的权限，权限有r,w,x三种

* 如果文件名之前多一个“ . ”，则代表这个文件为“隐藏文件”

* 对文件来讲，权限的性能为：

  * r：可读取此一文件的实际内容，如读取文本文件的文字内容等
  * w：可以编辑、新增或者是修改该文件的内容（但不含删除该文件）
  * x：该文件具有可以被系统执行的权限

* 对目录来说，权限的性能为： 

  * r （read contents in directory） 
  * w （modify contents of directory）
  *  x （access directory）

* FHS订定出来的四种目录特色为：shareable, unshareable, static, variable等四类

*  FHS所定义的三层主目录为：/, /var, /usr三层而已

*  绝对路径文件名为从根目录 / 开始写起，否则都是相对路径的文件名

## 第六章

* 绝对路径：“一定由根目录 / 写起”；相对路径：“不由 / 写起，而是由相对当前目录写起” 
* 特殊目录有：., .., -, ~, ~account需要注意
* 与目录相关的指令有：cd, mkdir, rmdir, pwd 等重要指令
* rmdir 仅能删除空目录，要删除非空目录需使用“ rm -r ”指令
* 使用者能使用的指令是依据 PATH 变量所规定的目录去搜寻的
* ls 可以检视文件的属性，尤其 -d, -a, -l 等选项
* 文件的复制、删除、移动可以分别使用：cp, rm , mv等指令来操作 
* 检查文件的内容（读档）可使用的指令包括有：cat, tac, nl, more, less, head, tail, od 等 
* cat -n 与 nl 均可显示行号，但默认的情况下，空白行会不会编号并不相同
* touch 的目的在修改文件的时间参数，但亦可用来创建空文件

## 第七章

* 一个可以被挂载的数据通常称为“文件系统, filesystem”而不是分区 （partition）

* 基本上 Linux 的传统文件系统为 Ext2 ，该文件系统内的信息主要有：

  * superblock：记录此 filesystem 的整体信息，包括inode/block的总量、使用量、剩余量， 

    以 及文件系统的格式与相关信息等

  * inode：记录文件的属性，一个文件占用一个inode，同时记录此文件的数据所在的 block 号 码
  * block：实际记录文件的内容，若文件太大时，会占用多个 block

* Ext2文件系统主要有：boot sector, superblock, inode bitmap, block bitmap, inode table, data 

  block 等六大部分

* 分区时，应使用 parted 检查分区表格式，再判断使用 fdisk/gdisk 来分区，或直接使用 parted 分区

## 第八章

* 压缩文件的扩展名大多是：“.gz, .bz2, .xz, .tar, .tar.gz, .tar.bz2, *.tar.xz”
* 常见的压缩指令有 gzip, bzip2, xz。压缩率最佳的是 xz，若可以不计时间成本，建议使用 xz 进行压缩
* tar 可以用来进行文件打包，并可支持 gzip, bzip2, xz 的压缩。 
* 压 缩：tar -Jcv -f filename.tar.xz 要被压缩的文件或目录名称 
* 查 询：tar -Jtv -f filename.tar.xz 
* 解压缩：tar -Jxv -f filename.tar.xz -C 欲解压缩的目录

## 第九章

* vi 有三种模式，一般指令模式可变换到编辑与命令行界面，但编辑模式与命令行界面不能互换
* 常用的按键有i, [Esc], :wq 等
* Linux 下面的配置文件多为文本文件，故使用 vim 即可进行设置编辑
* vim 可视为程序编辑器，可用以编辑 shell script, 配置文件等，避免打错字
* vi 为所有 unix like 的操作系统都会存在的编辑器，且执行速度快速
* 若使用 vim 来撰写网页，若需要 CSS 元素数据，可通过 [crtl]+x, [crtl]+o 这两个连续组合按键来取得关键字
* vim 的环境设置可以写入在 ~/.vimrc 文件中

# 


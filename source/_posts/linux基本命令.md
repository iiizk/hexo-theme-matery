---
title: linux基本命令
date: 2022-03-25 21:01:51
tags:
---
##	基本命令
### 关机

```shutdown -h now       立刻关机```
```shutdown -h 10        10分钟后关机```
```poweroff              立刻关机```

### 重启
`shutdown -r now       立刻重启`
`shutdown -r 10        10分钟后重启`
`reboot                立刻重启`

### 目录切换cd
`cd /                  切换到根目录`
`cd ..                 切换到上一级目录`
`cd ~                  切换到home目录`
`cd -                  切换到上次访问的目录`

### 目录查看ls
`ls                    查看当前目录下的所有目录和文件`
`ls -a            	 查看当前目录下的所有目录和文件（包括隐藏的文件）`
`ls -l 或 ll           列表查看当前目录下的所有目录和文件（列表查看，显示更多信息）`
`ls -il				查看当前目录文件的详细信息`

### 目录操作
`mkdir file         在当前目录下创建一个名为file的目录`

### 查看文件内容命令
### 功能：分页显示命令more
```more file```

功能：显示文件的最后几行tail
`tail -n 10 a.txt    显示文件a.txt文件的最后10行`

功能：创建一个空文件touch
`touch a.txt         在当前目录下创建一个名为a.txt的文件`

### 修改文件 vi或vim
`【vi编辑器的3种模式】`
```
基本上vi可以分为三种状态，分别是命令模式（command mode）、插入模式（Insert mode）和底行模式（last line mode），各模式的功能区分如下：
1) 命令行模式command mode）
      控制屏幕光标的移动，字符、字或行的删除，查找，移动复制某区段及进入Insert mode下，或者到 last line mode。
      命令行模式下的常用命令：
      【1】控制光标移动：↑，↓，j
      【2】删除当前行：dd 
      【3】查找：/字符
      【4】进入编辑模式：i o a
      【5】进入底行模式：:
      
2) 编辑模式（Insert mode）
      只有在Insert mode下，才可以做文字输入，按「ESC」键可回到命令行模式。
      编辑模式下常用命令：
      【1】ESC 退出编辑模式到命令行模式；
      
3) 底行模式（last line mode）
     将文件保存或退出vi，也可以设置编辑环境，如寻找字符串、列出行号……等。
     底行模式下常用命令：
     【1】退出编辑：   :q
     【2】强制退出：   :q!
     【3】保存并退出：  :wq
```

### mv 和 cp
```
一、重命名目录
    命令：mv 当前目录  新目录

二、剪切目录
    命令：mv 目录名称 目录的新位置
    示例：将/tmp目录下的aa目录剪切到/usr目录下面     mv /tmp/aa /usr

三、拷贝目录
    命令：cp -r 目录名称 目录拷贝的目标位置   -r代表递归
    示例：将/tmp目录下的aa目录复制到/usr目录下面     cp -r /tmp/aa  /usr
    注意：cp命令不仅可以拷贝目录还可以拷贝文件，压缩包等，拷贝文件和压缩包时不用写-r递归
文件的查看命令：cat/more/less/tail
```

### cat：看最后一屏
`示例：使用cat查看aaa.txt文件，只能显示最后一屏内容`
`cat aaa.txt`

### more：百分比显示
`示例：使用more查看aaa.txt文件，可以显示百分比，回车可以向下一行，空格可以向下一页，q可以退出查看`
`more aaa.txt`

### less：翻页查看
`示例：使用less查看aaa.txt文件，可以使用键盘上的PgUp和PgDn向上    和向下翻页，q结束查看`
`less aaa.txt`

## tail：指定行数或者动态查看
`示例：使用tail -10 查看aaa.txt文件的后10行，Ctrl+C结束  `
`tail -10 aaa.txt`

### find
```
find . -name "*.log" -ls  在当前目录查找以.log结尾的文件，并显示详细信息。 
find /etc/ -perm 600   查找/etc/目录下权限为600的文件 
find . -type f -name "*.log"  查找当目录，以.log结尾的普通文件 
find . -type d | sort   查找当前所有目录并排序 
find . -size +200M  查找当前目录大于100M的文件
```

### 清屏
`ctrl + l`
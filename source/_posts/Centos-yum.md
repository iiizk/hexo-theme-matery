---
title: Centos-yum
date: 2022-04-12 23:52:21
tags:
---
# 各版本源配置列表
```
CentOS5
wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.cloud.tencent.com/repo/centos5_base.repo
CentOS6
wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.cloud.tencent.com/repo/centos6_base.repo
CentOS7
wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.cloud.tencent.com/repo/centos7_base.repo
CentOS8
wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.cloud.tencent.com/repo/centos8_base.repo

更新缓存
yum clean all
yum makecache
```


## 以Centos6.5为列
`cd /etc/yum.repos.d`
这里的`CentOS-Base.repo`yum源有问题我们可以先备份一个
`cp CentOS-Base.repo`
## 方法1
### 这个是腾讯yum源
`wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.cloud.tencent.com/repo/centos6_base.repo`

## （这个上面是一样的yum源）
这是github推荐电脑登录下载下来再上传到linux中
怕失效自己备份了个
`https://github.com/iiizk/download/releases/download/centos/CentOS-Base.repo.bak6.repo`
改名
```
mv CentOS-Base.repo.bak6.repo CentOS-Base.repo
mv CentOS-Base.repo /etc/yum.repos.d/
```
## 方法2
### 这个是我自己修改的yum源（包括全部）
这是是打包好的全部  也是giuhub
`https://github.com/iiizk/download/releases/download/centos/CentOS-Base.repo.tar-6.tar`

```
解包
tar -xvf CentOS-Base.repo.tar-6.tar

改文件夹权限
chmod 755 CentOS-Base.repo
cd CentOS-Base.repo

改文件权限
chmod 644 *
mv * /etc/yum.repos.d/
```
## 最后
这里好了之后
```
清除缓存
yum clean all
建立元数据
yum makecache
测试
yum repolist
```


# Centos8 yum 源配置
### yum安装软件时，提示无法从AppStream下载

```
备份
mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup.3

下载
wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.cloud.tencent.com/repo/centos8_base.repo

清理之前的yum缓存
yum clean all

建立新的缓存
yum makecache

```
### yum makecache的时候报错了
`Centos8 比Centos7多了一个 CentOS-AppStream.repo`

`查看更新后的CentOS-Base.repo文件找到更新后CentOS-Base.repo中[AppStream]标签内的内容并复制`
`打开CentOS-AppStream.repo，注释掉原有内容，并插入新内容`

```
[AppStream]
name=Qcloud centos AppStream - $basearch
baseurl=http://mirrors.cloud.tencent.com/centos/$releasever/AppStream/$basearch/os/
enabled=0
gpgcheck=1
gpgkey=http://mirrors.cloud.tencent.com/centos/RPM-GPG-KEY-CentOS-Official
```

### 重新运行yum makecache
---
title: 二战理解linux
date: 2023-06-08 20:53:35
tags: linux
---


## 一些文件夹的名字
- **/bin**：
  常用命令目录
- **/boot：**
  核心文件
- **/dev ：**
  Device，Linux 的外部设备
- **/home**：
  主目录
- **/lib**：
  Library基本的动态连接共享库
- **/root**：
  管理员主目录
- **/tmp**：
  存放临时文件的
- **/usr**：
  类似program files目录
- **/usr/bin：**
  系统用户的应用程序
- **/var**：
  变量库
- **/run**：
  临时文件系统

## 命令
### 目录的
- **ls**:
 列目录 
  -al全部，大概这样
```linux
  drwxr-xr-x  20 root root       4096  6月  5 22:58 .
   drwxr-xr-x  20 root root       4096  6月  5 22:58 ..
   lrwxrwxrwx   1 root root          7  6月  5 22:54 bin -> usr/bin
   drwxr-xr-x   4 root root       4096  6月  8 21:10 boot
   drwxrwxr-x   2 root root       4096  6月  5 22:58 cdrom
   drwxr-xr-x  19 root root       4140  6月  8 20:42 dev
   drwxr-xr-x 130 root root      12288  6月  8 21:23 etc
   drwxr-xr-x   3 root root       4096  6月  5 23:00 home
……
```
- **cd、mkdir、cp、mv**:
 不解释
```linux
 mkdir -m配权限 -p连着它的上级一起创
```
```linux
mv -f强制-i询问覆盖
```
```linux
cp -p完全复制连带着属性-f强制-s快捷方式
```
- **pwd**:
 显示当前地址
- **rm**:
 删文件
```linux
rm -f强制-i删前询问-r递归也就是可以杀文件夹
```
### 看文件的
- **cat**:
 从第一行显示
```linux
cat -b列出有效行号-E显示$终止符-n列出包括空白行号-v列出特殊字符
```
- **tac**:
 反向显示
- **less**:
 一页一页翻
  pagedown/up：翻页
  /字串或者？字串：向上/向下搜索
  q：离开
- **head/tail**：
 正向/反向取出文件前几行
```linux
  head -n 数字：显示几行
```
### 下载
```linux
sudo apt install 软件
```
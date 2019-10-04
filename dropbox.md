# 安装 dropbox

## 安装 docutils

```sh
pip3 install docutils
```

## 下载最新 dropbox for linux 源码

选择最新版本

[dropbox linux download](https://linux.dropbox.com/packages/)

## 解压缩
```sh
tar xjf ./nautilus-dropbox-1.6.1.tar.bz2
```

## 安装三部曲
```sh
./configure
make
sudo make install
```

## 在线安装客户端

```sh
dropbox start -i
```

## 开机启动

```sh
dropbox autostart y
```
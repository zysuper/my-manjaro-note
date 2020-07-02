# 安装输入法

## 使用 ibus 拼音 + 搜狗短语库

```sh
sudo pacman -S ibus-pinyin
```

下载 [搜狗短语库](http://code.google.com/p/hslinuxextra/downloads/list)

```sh
cd /usr/share/pyzy/db
# 拷贝下载的短语库到这个路径.
sudo cp downloaded.db ./local.db
# 重启 bus.
ibus restart
```

## 百度输入法

### 安装

```sh
 yay -S fcitx-baidupinyin
 cp -r /tmp/data ~/.config/BaiduPY.user
 sudo pacman -S fcitx-configtool
```

### 修改显示字体

```sh
cd /home/zysuper/.config/fcitx/baidupy
vim bdconf
```

修改文件 bdconf

```ini
[BaiduPinyin]
...
FontSize=14
```

## 安装小企鹅输入法 + sunpinyin + 导入 sougou 细胞库

```sh
sudo pacman -S fcitx-im
sudo pacman -S fcitx-configtool
sudo pacman -S fcitx-sunpinyin
```

## 导入 sougou 细胞库

### 下载细胞库

[-> 搜狗输入法细胞库 <-](https://pinyin.sogou.com/)

### 细胞库导入

```sh
git clone https://github.com/sunpinyin/sunpinyin
cd python/importer
python2.7 import_sogou_celldict.py ./computer2.scel
```

## 正确配置环境变量

vi ~/.xprofile

```sh
export GTK_IM_MODULE=fcitx
export QT_IM_MODULE=fcitx
export XMODIFIERS="@im=fcitx"
```

## 安装搜狗输入法 qt5 (推荐)

### 前置检查

如果你之前安装了 `fcitx-lilydjwg-git`, `fcitx-sogoupinyin`,请先卸载掉。

```sh
yay -S aur/fcitx-sogouimebs
sudo pacman -S fcitx-configtool
```

## 正确配置环境变量

vi ~/.xprofile

```sh
export GTK_IM_MODULE=fcitx
export QT_IM_MODULE=fcitx
export XMODIFIERS="@im=fcitx"
```

## 安装 fcitx5 输入法 (不推荐)  

```sh
sudo pacman -S yay 
```

## 开启 aur 源

## 安装以下包

* fcitx5-git 输入法基础框架主程序
* fcitx5-chinese-addons-git 简体中文输入的支持，云拼音
* fcitx5-gtk-git gtk 程序的支持
* fcitx5-qt4-git qt4 的支持
* fcitx5-qt5-git qt5 的支持

## config ~/.xprofile

```sh
export GTK_IM_MODULE=fcitx5
export XMODIFIERS=@im=fcitx5
export QT_IM_MODULE=fcitx5
fcitx5 &
```



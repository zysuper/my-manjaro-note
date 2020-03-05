# 安装输入法

## 安装搜狗输入法

```sh
sudo pacman -S fcitx-lilydjwg-git 
sudo pacman -S fcitx-sogoupinyin
sudo pacman -S fcitx-configtool
```

## 正确配置环境变量

vi ~/.xprofile

```sh
export GTK_IM_MODULE=fcitx
export QT_IM_MODULE=fcitx
export XMODIFIERS="@im=fcitx"
```

## 安装 fcitx5 输入法   

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



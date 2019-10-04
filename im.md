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
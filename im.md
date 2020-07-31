# 安装输入法

## 安装 fcitx5 输入法 (推荐)  

```sh
sudo pacman -S yay
```

### 开启 aur 源

### 安装以下包 (!! 非 kde 环境。 kde 环境自己看: [Fcitx5 Config](https://wiki.archlinux.org/index.php/Fcitx5_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87)))

```sh
# 安装 各种通用输入法，以及皮肤，输入法模块
sudo pacman -S fcitx5 fcitx5-chinese-addons fcitx5-material-color fcitx5-gtk
# 配置工具(!!! 非 kde 环境)，会连带安装 fcitx5 相关组件
yay -S fcitx5-config-qt-git
# 安装词库
sudo pacman fcitx5-pinyin-moegirl
yay -S fcitx5-pinyin-zhwiki
```

### 修改 .xprofile

```
export GTK_IM_MODULE=fcitx5
export XMODIFIERS="@im=fcitx5"
export QT_IM_MODULE=fcitx5
XMODIFIERS DEFAULT=@im=fcitx5
```

### 增加启动项目

~/.config/autostart/fcitx5.desktop

```
[Desktop Entry]
Name[ca]=Fcitx 5
Name[da]=Fcitx 5
Name[de]=Fcitx 5
Name[ko]=Fcitx 5
Name[zh_CN]=Fcitx 5
Name=Fcitx 5
GenericName[ca]=Mètode d'entrada
GenericName[da]=Inputmetode
GenericName[de]=Eingabemethode
GenericName[ja]=入力メソッド
GenericName[ko]=입력기
GenericName[ru]=Метод ввода
GenericName[zh_CN]=输入法
GenericName[zh_TW]=輸入法
GenericName=Input Method
Comment[ca]=Mètode d'entrada estàndard
Comment[da]=Start inputmetode
Comment[de]=Eingabemethode starten
Comment[ko]=입력기 시작
Comment[zh_CN]=启动输入法
Comment=Start Input Method
Exec=/usr/bin/fcitx5
Icon=fcitx
Terminal=false
Type=Application
Categories=System;Utility;
StartupNotify=false
X-GNOME-AutoRestart=true
X-GNOME-Autostart-Notify=false
X-KDE-autostart-after=panel
X-KDE-StartupNotify=false
```

### 重启系统后、用 fcitx5-config-qt 配置

* 添加拼音输入法
* 开启预测
* 开启云拼音

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

## config ~/.xprofile

```sh
export GTK_IM_MODULE=fcitx5
export XMODIFIERS=@im=fcitx5
export QT_IM_MODULE=fcitx5
fcitx5 &
```



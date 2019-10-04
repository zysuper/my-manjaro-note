# 安装 deepin QQ

## 安装软件

两种二选一

```sh
pacman -S deepin.com.qq.office # TIM 版本
pacman -S deepin.com.qq.im # QQ 版本
```

## 字体不清晰补丁

### 打开软件中心的 aur 源

### 安装 yay

```sh
pacman -S yay-git
```

### 安装 aur freetype 32 infinality & ultimate 补丁

```sh
yay -S lib32-freetype2-infinality-ultimate
```

### 解决 hidpi 下字体太小问题

```sh
env WINEPREFIX="$HOME/.deepinwine/Deepin-TIM" winecfg # TIM 版本
env WINEPREFIX="$HOME/.deepinwine/Deepin-QQ" winecfg # QQ 版本
```

使用 winecfg 修改 显示 -> 屏幕分辨率 -> 120 dpi

## 解决 System Tray 问题

从 gnome 3.3 之后，著名的 TopIconPlus 可能处于不可用状态，需要使用 Tray icons 扩展

[goto tray icons](https://extensions.gnome.org/extension/1503/tray-icons/)
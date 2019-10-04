# 配置源

## 选择上海交大源

```sh
sudo pacman-mirrors -i -c China -m rank
```

## 更新

```sh
sudo pacman -Syy
```

## 更新系统到最新

```sh
sudo pacman -Syu
```

## 添加 archlinux cn

```sudo vi /etc/pacman.conf```

```sh
[archlinuxcn]
SigLevel = Optional TrustedOnly
Server = https://mirrors.sjtug.sjtu.edu.cn/archlinux-cn/$arch
```

## 再更新，安装证书

```sh
sudo pacman -Syy
sudo pacman -S archlinux-keyring
sudo pacman -S archlinuxcn-keyring
```

# 修复 jetbrain 输入法不跟随问题

## 下载 JetBrainsRuntime 源码

```sh
git clone https://github.com/JetBrains/JetBrainsRuntime.git
```

## 应用 patch

patch的使用方式:

```sh
git checkout cfc3e87f2ac27a0b8c78c729c113aa52535feff6
git apply idea.patch
```

## 增加 OpenJFX 模块

```sh
sudo pacman -S cmake ruby

# 下载 openJFX 源码
git clone https://github.com/openjdk/jfx.git

# 编译 openJFX
cd rt
chmod a+x gradlew
./gradlew -PCOMPILE_WEBKIT=true
```

## 编译 JetBrainsRuntime

```sh
sh ./configure --disable-warnings-as-errors
```

## 修复 idea 使用 fcitx5 输入框没法重建问题

Help -> Edit Custom VM Options

```properties
-Drecreate.x11.input.method=true
```
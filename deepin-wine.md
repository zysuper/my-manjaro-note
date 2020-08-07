# 如何使用 deepin wine 运行 windows 程序

## 拷贝一份 Deepin-qq 环境

```sh
cp -r ~/.deepinwine/Deepin-QQ ~/.bottle
```

## 用 deepin wine 运行 exe 程序

```sh
WINEPREFIX=~/.bottle deepin-wine your-windows-program.exe
```
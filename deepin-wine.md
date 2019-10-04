# 如何实用 deepin wine 运行 windows 程序

1. 拷贝一份 Deepin-qq 环境

```sh
cp -r ~/.deepinwine/Deepin-QQ ~/.bottle
```

2. 用 deepin wine 运行 exe 程序

```sh
WINEPREFIX=~/.bottle deepin-wine your-windows-program.exe
```
# 解决 hidpi 下 vscode 输入法位置不对的问题

修改 `/usr/share/applications/visual-studio-code.desktop`，

增加 `GDK_SCALE=1 GDK_DPI_SCALE=1`

```
[Desktop Entry]
Exec=env GDK_SCALE=1 GDK_DPI_SCALE=1 /opt/visual-studio-code/code %f
```
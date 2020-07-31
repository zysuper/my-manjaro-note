# gnome-shell 扩展
[-> Hide Top Bar <-](https://github.com/mlutfy/hidetopbar)

## 配置 alt-tab 在窗口间切换

1. 打开 dconf-editor
1. 进入 `org/gnome/desktop/wm/keybindings` 
1. 删除 switch-applications 的 `<Alt>Tab`，配置 switch-windows 增加 `<Alt>Tab`
1. 重启 gnome. (Alt+F2, 输入 r)

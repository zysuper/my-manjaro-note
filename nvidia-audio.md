# 修复 nvidia 显卡外接显示器没有音频输出问题

修改文件 /etc/udev/rules.d/90-mhwd-prime-powermanagement.rules

注释掉 udev 移除 nvidia audio 的代码

```sh
# ACTION=="add", SUBSYSTEM=="pci", ATTR{vendor}=="0x10de", ATTR{class}=="0x040300", ATTR{remove}="1" 
```
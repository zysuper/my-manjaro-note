# 微信程序

```sh
yay -S com.qq.weixin.deepin
```

## 微信输入框字体为方框

方法一： 修改 /home/zysuper/.deepinwine/Deepin-TIM/system.reg, 增加 `msyh.ttf,Microsoft Yahei\0`

```regedit
[Software\\Microsoft\\Windows NT\\CurrentVersion\\FontLink\\SystemLink] 1605770229
#time=1d6be43fe6bc47e
"Lucida Sans Unicode"=str(7):"msyh.ttf,Microsoft Yahei\0SIMSUN.TTC,SimSun\0MINGLIU.TTC,PMingLiu\0MSGOTHIC.TTC,MS UI Gothic\0BATANG.TTC,Batang\0"
"Microsoft Sans Serif"=str(7):"msyh.ttf,Microsoft Yahei\0SIMSUN.TTC,SimSun\0MINGLIU.TTC,PMingLiu\0MSGOTHIC.TTC,MS UI Gothic\0BATANG.TTC,Batang\0"
"Tahoma"=str(7):"msyh.ttf,Microsoft Yahei\0SIMSUN.TTC,SimSun\0MINGLIU.TTC,PMingLiu\0MSGOTHIC.TTC,MS UI Gothic\0BATANG.TTC,Batang\0"
```

方法二： 通过 regedit 修改：

```sh
env WINEPREFIX="$HOME/.deepinwine/Deepin-TIM" /home/$USER/.deepinwine/deepin-wine5-stable/bin/wine regedit
```

`Software\\Microsoft\\Windows NT\\CurrentVersion\\FontLink\\SystemLink`

每种字体都增加 `msyh.ttf,Microsoft Yahei`
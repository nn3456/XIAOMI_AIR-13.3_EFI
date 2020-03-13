小米efi备份，小米笔记本 18年款。触摸板 键盘 亮度都正常
# 硬件信息
+ 电脑品牌： XiaoMi
+ 型号：Air 13.3 指纹独显版 2018 款
+ CPU：i5-8250U
+ 核显：intel UHD Graphics 620
+ 独显：GeForce MX150
+ 内存：单条8GB 2400 MHz DDR4
+ 硬盘：250G SSD

当前系统版本为10.15.3，其他版本未测试。
使用时请自行生成三码，现在激活iMessage都不用白码了。注意先弄好网卡内建。网卡mac地址可以通过编译ACPI/SSDT-RMNE修改，详细信息查看[大神帖子](https://github.com/RehabMan/OS-X-Null-Ethernet)
```bash
# 内建网卡可能需要
sudo rm -rf /Library/Preferences/SystemConfiguration/NetworkInterfaces.plist
# 删掉设置--网络中所有连接并应用。然后重启电脑。
```
# 当前不完善的
+ 无线wifi仍然无解。参考[远景论坛](http://bbs.pcbeta.com/viewthread-1838489-1-1.html)，发布地址在[GitHub](https://github.com/a565109863/AppleIntelWiFi_Debug/releases)
+ 独立显卡无法工作，因为macOS不支持Optimus技术。使用SSDT-DDGPU	禁用
+ 指纹传感器无法工作。

# 已经正常使用的
+ 蓝牙驱动[参考远景论坛](http://bbs.pcbeta.com/viewthread-1838959-6-1.html)，访问不了的直接看[GitHub](https://github.com/zxystd/IntelBluetoothFirmware/releases/)吧。（注意如果定制过USB口，屏蔽过蓝牙的记得改回来，我就是踩了这个坑）
+ CPU睿频、变频正常
+ 核显UHD620正常，显存1536MB
+ 声音正常，可通过快捷键Fn-F2/F3调节
+ 亮度调节正常，可通过Fn-F4/F5调节
+ 原生电池管理正常
+ USB 2.0/3.0 正常，未定制，未测试睡眠和休眠
+ HDMI正常
+ 摄像头可正常使用

# 下一步
+ 定制USB
+ 转到opencore？
+ 等待大神驱动wifi

# WiFi解决方案
暂时使用USB外接WiFi（CF-WU810N），驱动在额外的包中。
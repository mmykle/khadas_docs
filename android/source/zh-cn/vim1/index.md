title: VIM1 文档
---

## VIM1
![image](/android/images/vim1/docs_vim1.jpg)

<ul class="nav nav-tabs" id="myTab" role="tablist">
  <li class="nav-item" role="presentation">
    <a class="nav-link active" id="front-tab" data-toggle="tab" href="#front-vim1" role="tab" aria-controls="front" aria-selected="true">Front(Blue)</a>
  </li>
  <li class="nav-item" role="presentation">
    <a class="nav-link" id="back-tab" data-toggle="tab" href="#back-vim1" role="tab" aria-controls="back" aria-selected="false">BACK(RED)</a>
  </li>
  <li class="nav-item" role="presentation">
    <a class="nav-link" id="button-tab" data-toggle="tab" href="#button-vim1" role="tab" aria-controls="button" aria-selected="false">BUTTONS</a>
  </li>
  <li class="nav-item" role="presentation">
    <a class="nav-link" id="led-tab" data-toggle="tab" href="#led-vim1" role="tab" aria-controls="led" aria-selected="false">Indicator LEDs</a>
  </li>
  <li class="nav-item" role="presentation">
    <a class="nav-link" id="gpio-tab" data-toggle="tab" href="#gpio-vim1" role="tab" aria-controls="gpio" aria-selected="false">GPIO Pinout</a>
  </li>
</ul>
<div class="tab-content" id="myTabContent">
<div class="tab-pane fade show active" id="front-vim1" role="tabpanel" aria-labelledby="front-tab">

||设备名称|描述说明|
|---:|:---|:---|
|1|USB-A|USB 2.0接口,最大输出电流500mA|
|2|RJ-45|10/100 Mbps的网口|
|3|HDMI|支持3D,HDR,CEC以及HDCP2.2的HDMI接口|
|4|USB-C|USB2.0 OTG接口,[5V输出](https://www.khadas.com/product-page/power-adapter),[可用于升级固件](/android/zh-cn/vim1/UpgradeViaUSBCable.html)|
|5|USB-A|USB 2.0接口,最大输出电流900mA|
|6|风扇座子|PWM控制的4线制风扇|
|7|reset按键|用于强制重启板子,按下会直接复位|
|8|function按键|快速短按3下进入[MaskROM模式](/android/zh-cn/vim1/BootIntoUpgradeMode.html)或从外部介质启动|
|9|power按键|用于关机或者配合其他按键使用|
|A|4个M2插孔|用于使用[散热器](https://www.khadas.com/product-page/new-vim-heatsink)和[DIY外壳](https://www.khadas.com/product-page/diy-case)时的固定|
|B|RTC电池接口|硬件时钟电池的接口|
|C|[40脚的GPIO](/android/zh-cn/vim1/GPIOPinout.html)|可用于控制[GPIO](/android/zh-cn/vim1/AccessGpio.html)或者与[toneboard](https://www.khadas.com/product-page/tone-board)连接|
|D|红外模块|可用于与[khadas遥控器](https://www.khadas.com/product-page/ir-remote)通信|
|E|LED灯|用于指示板子的状态|
|F|天线座子|用于插wifi和蓝牙的天线|
</div>
<div class="tab-pane fade" id="back-vim1" role="tabpanel" aria-labelledby="back-tab">

||设备名称|描述说明|
|---:|:---|:---|
|1|[VIN](https://www.khadas.com/product-page/vin-to-vin-cable)|5V电压输出|
|2|SD卡插座|作为外部存储器|
|3|M寄存器触点|[强制进入MaskROM模式](/android/zh-cn/vim1/BootIntoUpgradeMode.html)|
|4|XPWR焊盘|用于连接使用外部电源|
</div>
<div class="tab-pane fade" id="button-vim1" role="tabpanel" aria-labelledby="button-tab">

|Reset|Function|Power|描述说明|
|:---:|:---:|:---:|:---|
|x|||强制重启VIM1|
||x||[进入升级模式(TST模式)](/android/zh-cn/vim1/BootIntoUpgradeMode.html)|
|||x|开机或者唤醒VIM1|
|x||x|[进入升级模式(按键模式)](/android/zh-cn/vim1/BootIntoUpgradeMode.html)|
|x|x|x|[清除EMMC](/android/zh-cn/vim1/EraseEMMC.html)|
</div>
<div class="tab-pane fade" id="led-vim1" role="tabpanel" aria-labelledby="led-tab">

|颜色|状态|含义|
|---:|:---:|:---|
|蓝色|关闭|电源关闭|
||常亮|已连接电源,板子处于关机状态|
|白色|关闭|板子已关机|
||常亮|板子处于开机状态|
|红灯|None|None|

上述行为是默认的，用户可以更改。例如，可以使白灯闪烁或呼吸。有关如何通过所喜爱的操作系统（每个操作系统都不同）编程的更多信息可通过[forum.khadas.com](https://forum.khadas.com)咨询。
</div>
<div class="tab-pane fade" id="gpio-vim1" role="tabpanel" aria-labelledby="gpio-tab">

![Image of Vim GPIO](/android/images/vim1/vim_pinout.png)
</div>
</div> 


{% note info 注意 %}

* `PIN17-20`: 串口调试
* `PIN29-33`: I2S
* `PIN36`: 32.768KHz时钟输出
* `PIN38`: 系统电源使能管脚

{% endnote %}

## VIM1 电源选择
尽管您的VIM1 SBC与各种类型的电源兼容，但这些是最佳性能输出和稳定性的推荐规格。

1. 5V,2A 电源适配器
2. Type-C数据线

**更多：**
* [Khadas Shop - 电源适配器](https://www.khadas.com/product-page/power-adapter)
* [Khadas Shop - Type-C数据线](https://www.khadas.com/product-page/usb-c-cable)
* [Khadas VIMs 外部供电接口](/android/zh-cn/vim1/ExtraPowerInput.html)
* [Khadas VIM 规格](https://www.khadas.com/vim)

## 显示器　&& 用户输入
当您需要将VIM1 SBC连接到外部显示器+键盘鼠标+遥控器，以用作台式计算机或媒体中心时，这些选项非常有用

1. 4K HDMI 2.0 的数据线
2. 兼容1080P和4K的显示器
3. 无线的鼠标和键盘
4. 兼容CEC的遥控器

**更多：**
[Khadas Shop - HDMI数据线](https://www.khadas.com/product-page/hdmi-cable)
[Khadas Shop - 遥控器](https://www.khadas.com/product-page/ir-remote)
[亚马逊－无线鼠标和键盘](https://www.amazon.com/s/ref=nb_sb_noss?url=search-alias%3Delectronics&field-keywords=wireless+keyboard+and+mouse&rh=n%3A172282%2Ck%3Awireless+keyboard+and+mouse)

## 使用Type-C升级EMMC系统
如果您想使用笔记本电脑或台式电脑升级存储在EMMC存储器中的VIM1 SBC操作系统，则需要这些项目。例如，将启动操作系统从android改为ubuntu，或者安装更具特色的第三方操作系统。

1. 常见Tpye-C数据线 (传统PC)
2. 两头Type-C的数据线 (现代PC)

**更多：**
* [通过USB升级固件](/android/zh-cn/vim1/UpgradeViaUSBCable.html)
* [进入升级模式](/android/zh-cn/vim1/BootIntoUpgradeMode.html)

**固件**
* [安卓固件](/android/zh-cn/vim1/FirmwareAndroid.html)
* [U-Boot](/android/zh-cn/vim1/FirmwareUboot.html)
* [Third Party OSes](/android/zh-cn/vim1/FirmwareThirdparty.html)

## 观看电影，扩展内部emmc存储
如果您希望将VIM1 SBC用作媒体中心，用于存储/下载大型电影文件，这些项目非常有用。一个microDXC的UHS-I卡很贵，但它的速度也足以支持4K视频播放。此外，您还可以连接外部USB-2.0 SSD或HDD以存储整个媒体库。

1. 不小于64GB的USB-2.0 HDD/SSD
2. 不小于64GB的*microSDXC UHS-I* SD-Card

**更多:**
* [Amazon - Samsung T5 Portable SSD](https://www.amazon.com/Samsung-T5-Portable-SSD-MU-PA1T0B/dp/B073H552FJ/ref=sr_1_1_sspa?ie=UTF8&qid=1543995277&sr=8-1-spons&keywords=external+usb+ssd&psc=1)
* [Amzon - microSDXC UHS-I SD-Card](https://www.amazon.com/s/ref=nb_sb_noss?url=search-alias%3Daps&field-keywords=microSDXC+UHS-I&rh=i%3Aaps%2Ck%3AmicroSDXC+UHS-I)


# 软件开发/高级CRACH恢复
在系统完全崩溃需要手动恢复的极端情况下，需要使用mregister重置VIM1 SBC。USB串行调试工具对于开发人员调>试复杂软件问题也很有用。

1. 可导电的金属镊子（用于通过mregister重置死掉的sbc）
2. USB串行调试工具（用于诊断软件/硬件问题）

**更多:**
* [升级模式](/android/zh-cn/vim1/BootIntoUpgradeMode.html)
* [亚马逊－金属镊子](https://www.amazon.com/s/ref=nb_sb_noss_2?url=search-alias%3Daps&field-keywords=metal+tweezers)
* [亚马逊-USB调试工具](https://www.amazon.com/s/ref=nb_sb_noss?url=search-alias%3Daps&field-keywords=usb+serial+debug+tool&rh=i%3Aaps%2Ck%3Ausb+serial+debug+tool)

## VIM1相关网页
更多的相关信息，请查看我们的网页，阅读文档，或者到论坛浏览以及提问。
* [VIM1网站首页](https://www.khadas.com/vim)
* [VIM1论坛页](https://forum.khadas.com/c/khadas-vim)

## VIM1 介绍视频
{% youtube dLAX8nwcTvo %}


title: VIM1 Beginners Guide
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

||Component|Purpose|
|---:|:---|:---|
|1|USB-A|USB 2.0 speed, 500mA max output|
|2|RJ-45|10/100 Mbps Ethernet|
|3|HDMI|HDMI 2.0b with 3D, HDR, CEC and HDCP 2.2|
|4|USB-C|USB 2.0 OTG and [5V power input](https://www.khadas.com/product-page/power-adapter), can be used for [upgrading the OS](/android/vim1/UpgradeViaUSBCable.html)|
|5|USB-A|USB 2.0 speed, 900mA max output|
|6|Fan Header|4-wire [fan](https://www.khadas.com/product-page/3705-cooling-fan) header utilising pulse width modulation|
|7|Reset Button|Force reboot your VIM1 in the event of a system freeze|
|8|Function Button|Press this 3 times in 2 seconds to [enter MaskROM mode](/android/vim1/BootIntoUpgradeMode.html)|
|9|Power Button|This button turns on your VIM1|
|A|M2x4 Mounting Point|For mounting to [cases](https://www.khadas.com/product-page/diy-case) and [heatsinks](https://www.khadas.com/product-page/new-vim-heatsink)|
|B|RTC Battery Header|Header for attaching a battery for the real time clock|
|C|[40-Pin GPIO](/android/vim1/GPIOPinout.html)|Learn how to access the GPIO from [here](/android/vim1/AccessGpio.html), or use it to add a [Toneboard](https://www.khadas.com/product-page/tone-board)|
|D|Infrared Module|2-channel infrared receiver for use with [Khadas IR remote](https://www.khadas.com/product-page/ir-remote)|
|E|LEDs|Status indicator LEDs|
|F|I-Pex Wi-Fi / Bluetooth Connector|Wi-Fi / BT Antenna connector|
</div>
<div class="tab-pane fade" id="back-vim1" role="tabpanel" aria-labelledby="back-tab">

||Component|Purpose|
|---:|:---|:---|
|1|[VIN](https://www.khadas.com/product-page/vin-to-vin-cable)|5V power input|
|2|Micro-SD Card Slot|for extra storage|
|3|M-Register|Allows the EMMC to [enter MaskROM mode](/android/vim1/BootIntoUpgradeMode.html)|
|4|XPWR Pads|Connect an external power switch using these pads|
</div>
<div class="tab-pane fade" id="button-vim1" role="tabpanel" aria-labelledby="button-tab">

|Reset|Function|Power|Purpose|
|:---:|:---:|:---:|:---|
|x|||Force Reboot VIM1
||x||[Enter Upgrade Mode (TST)](/android/vim1/BootIntoUpgradeMode.html)|
|||x|Power On/Wake Up VIM1|
|x||x|[Enter Upgrade Mode (KEYS)](/android/vim1/BootIntoUpgradeMode.html)|
|x|x|x|[Erase EMMC](/android/vim1/EraseEMMC.html)|
</div>
<div class="tab-pane fade" id="led-vim1" role="tabpanel" aria-labelledby="led-tab">

|Colour|Behaviour|Meaning|
|---:|:---:|:---|
|Blue|OFF|Power source disconnected|
||Solid ON|Power source connected, SBC turned off|
|White|OFF|SBC turned off|
||Solid ON|SBC turned on|
|Red|None|None|

The above behaviours are default out-of-the-box, and can be altered by a user. For example the white LED can be made to blink or breathe. For more information on how to program them via your favourite OS (each OS is different), please consult with experts at [forum.khadas.com](https://forum.khadas.com).
</div>
<div class="tab-pane fade" id="gpio-vim1" role="tabpanel" aria-labelledby="gpio-tab">

![Image of Vim GPIO](/android/images/vim1/vim_pinout.png)
</div>
</div> 


{% note info Notice %}

* `PIN17-20`: for UART debugging
* `PIN29-33`: iomux for I2S
* `PIN36`   : 32.768KHz clock output
* `PIN38`   : enable signal for whole system power

{% endnote %}

## VIM1 Power Supply
Although your VIM1 SBC is compatible with various types of power supplies, these are the recommended specs for the best performance-output and stability.

1. 5V, 2000mA Power Adapter
2. USB-A to USB-C Cable

**Learn More:**
* [Khadas Shop - Power Adapter](https://www.khadas.com/product-page/power-adapter)
* [Khadas Shop - USB-C Cable](https://www.khadas.com/product-page/usb-c-cable)
* [Extra Power Input For Khadas VIMs](/android/vim1/ExtraPowerInput.html)
* [Khadas VIM Specifications](https://www.khadas.com/vim)

## Displays & User Input
These items are useful when you need to connect your VIM1 SBC to an external display + keyboard mouse + remote control, for use as a desktop computer or media center.

1. 4K HDMI 2.0 Cable
2. HDMI-Compatible 1080P/4K Monitor
3. Wireless USB Keyboard + Mouse
4. CeC-Compatible Remote Control

{% note warn Note %}
Please do not attach multiple cables with large heads that interfere with each other, as that may bend or twist the connectors, and this will cause intermittent connectivity issues after some time.
{% endnote %}

**Learn More:**
* [Khadas Shop - HDMI Cable](https://www.khadas.com/product-page/hdmi-cable)
* [Khadas Shop - Remote Control](https://www.khadas.com/product-page/ir-remote)
* [Amazon - Wireless Keyboard + Mouse](https://www.amazon.com/s/ref=nb_sb_noss?url=search-alias%3Delectronics&field-keywords=wireless+keyboard+and+mouse&rh=n%3A172282%2Ck%3Awireless+keyboard+and+mouse)

## Upgrading eMMC Operating System Using USB-Cable
You'll need these items if you want to use your laptop or desktop PC to upgrade your VIM1 SBC's operating system stored in its eMMC storage. For example, changing the bootup operating system from Android to Ubuntu, or installing a more exotic 3rd-party OS.

1. USB-A to USB-C Data Cable (Legacy Computers)
2. USB-C to USB-C Data Cable (Modern Computers)
3. Laptop / Desktop PC

**Learn More:**
* [Upgrade Firmware Using USB-C Cable](/android/vim1/UpgradeViaUSBCable.html)
* [Booting Into Upgrade Mode](/android/vim1/BootIntoUpgradeMode.html)

**Firmware Images:**
* [Android OS](/android/vim1/FirmwareAndroid.html)
* [U-Boot](/android/vim1/FirmwareUboot.html)
* [Third Party OSes](/android/vim1/FirmwareThirdparty.html)

## Software Development / Advanced Crash Recovery
Extreme cases of crash-recovery will require you to use the MRegister to reset your VIM1 SBC. A USB Serial Debug Tool is also useful for developers debugging complex software issues.

1. Conductive Metal Tweezers (For resetting a dead SBC via MRegister)
2. USB Serial Debug Tool (For diagnosing software/hardware issues)

**Learn More:**
* [MRegister Upgrade Mode](/android/vim1/BootIntoUpgradeMode.html)
* [Amazon - Metal Tweezers](https://www.amazon.com/s/ref=nb_sb_noss_2?url=search-alias%3Daps&field-keywords=metal+tweezers)
* [Amazon - USB Serial Debug Tool](https://www.amazon.com/s/ref=nb_sb_noss?url=search-alias%3Daps&field-keywords=usb+serial+debug+tool&rh=i%3Aaps%2Ck%3Ausb+serial+debug+tool)

## VIM1 Website
For more information, please see our website, read more documentation, or visit our forum.
* [Khadas VIM1 Homepage](https://www.khadas.com/vim)
* [Khadas VIM1 Forum](https://forum.khadas.com/c/khadas-vim)

## VIM1 Review Video
{% youtube dLAX8nwcTvo %}

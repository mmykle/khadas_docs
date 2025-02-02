title: 通过USB线安装系统到eMMC
---

{% note info 由于VIM系列操作方式基本上是一样的，所以本文档以VIM1为例进行说明。%}

{% endnote %}

所有VIM系列板子都有板载eMMC存储，可以通过USB烧录工具把系统安装到eMMC。


<ul class="nav nav-tabs" id="myTab" role="tablist">
  <li class="nav-item" role="presentation">
    <a class="nav-link active" id="win-tab" data-toggle="tab" href="#win" role="tab" aria-controls="win" aria-selected="true">在Windows下安装</a>
  </li>
  <li class="nav-item" role="presentation">
    <a class="nav-link" id="ubu-tab" data-toggle="tab" href="#ubu" role="tab" aria-controls="ubu" aria-selected="false">在Ubuntu下安装</a>
  </li>
</ul>
<div class="tab-content" id="myTabContent">
<div class="tab-pane fade show active" id="win" role="tabpanel" aria-labelledby="win-tab">

## 准备
* 下载升级工具[USB Upgrade Tool](https://dl.khadas.com/Tools/USB_Burning_Tool_v2.2.0.zip)并解压。
* 运行`setup_v2.x.x.exe`程序进行安装。
![image](/linux/images/vim1/usb_upgrade_tool_setup_v217_zh.png)

## 安装系统到eMMC

确保已经正确安装好升级工具，然后按照下面步骤进行升级：

1、打开升级工具`USB_Burning_Tool_v2.x.x.exe`，点击`File-->Import image`选择要升级的固件。
2、用USB-C线连接板子和PC电脑（默认板子上电会自动开机）。
3、进入固件[升级模式](BootIntoUpgradeMode.html)。
4、如果上面操作已正确执行，电脑端会发现板子升级设备，点击升级工具上的`开始`按钮开始固件升级,升级进度条100%时完成升级。

![image](/linux/images/vim1/usb_upgrade_tool_interface_v217_zh.png)

{% note info 提示 %}

* 先点击`停止`按钮再关闭升级工具。
* [外部供电要求](ExtraPowerInput.html)，部分电脑供电比较弱会导致升级失败。

{% endnote %}

</div>
<div class="tab-pane fade" id="ubu" role="tabpanel" aria-labelledby="ubu-tab">

## 准备

```bash
$ sudo apt-get install libusb-dev git parted
```

## 获取Ubuntu烧录工具

烧录工具在仓库[utils](https://github.com/khadas/utils)中。

```bash
$ git clone https://github.com/khadas/utils
```

如果你之前已经下载过`utils`仓库，那么你只需要更新到最新版本即可。

```bash
$ cd /path/to/utils
$ git pull
```

## 安装烧录工具

需要安装usb规则以及创建链接文件。

```bash
$ cd /path/to/utils
$ ./INSTALL
```

如果成功安装你会看到如下信息：

```bash
Installing Amlogic flash-tool...

===============================================

 Host PC: Ubuntu 16.04
 
 ===============================================
 
 Installing USB rules...
 [sudo] password for nick:
 Installing flash-tool...
 Done!
 
 Installing Rockchip flash-tool...
 
 ===============================================
         
 Host PC: Ubuntu 16.04
                 
 ===============================================
                   
 Installing USB rules...
 Installing flash-tool...
 Done!
 Installing Khadas burn
 Done!
```

{% note info 注意 %}

安装过程中需要root权限。

{% endnote %}

## 检查USB驱动
首先设置VIMs进入[升级模式](BootIntoUpgradeMode.html)，然后检查USB驱动：

```bash
$ lsusb | grep Amlogic
Bus 002 Devices 036: ID 1b8e:c003 Amlogic, Inc.
```

以上信息说明PC已经识别到了VIM3

## 安装系统到eMMC

有2个命令可以用于烧录固件：`burn-tool`和`aml-burn-tool`。

以烧录VIM3为例：

* 通过烧录命令`burn-tool`：

```bash
$ burn-tool -v aml -b VIM3 -i /path/to/image
```

* Amlogic平台专用烧录命令`aml-burn-tool`：

```bash
$ aml-burn-tool -b VIM3 -i /path/to/image
```

{% note info 注意 %}

烧录VIM3一定要指定`-b VIM3`参数，否则会失败。对于VIM1或VIM2不用指定。

{% endnote %}

如果烧录成功你会看到如下信息：

```bash
Rebooting the board ........[OK]
Unpacking image [OK]
Initializing ddr ........[OK]
Running u-boot ........[OK]
Create partitions [OK]
Writing device tree [OK]
Writing bootloader [OK]
Wiping  data partition [OK]
Wiping  cache partition [OK]
Writing boot partition [OK]
Writing data partition [OK]
Writing logo partition [OK]
Writing system partition [OK]
Do you want to reset the board? y/n [n]? y
Resetting board [OK]

```

更多请参考[文档](https://github.com/khadas/utils/tree/master/aml-flash-tool/docs)。

## 卸载烧录工具

```bash
$ cd /path/to/utils
$ ./UNINSTALL
```

</div>
</div>


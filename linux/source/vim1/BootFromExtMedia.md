title: Boot Images from External Media
---

There are several images that are designed to run from a SD Card or Thumbdrive (U-Disk) and are compatible with VIMs. For example:
* [Armbian with Debian / Ubuntu](https://www.armbian.com/download/?tx_maker=khadas)
* [CoreELEC](https://coreelec.org/)
* [LibreELEC](https://libreelec.tv/downloads_new/khadas-vim/)
* [Manjaro](https://forum.khadas.com/t/manjaro-linux-desktop-environment-for-vim1-vim3/3945)
* [Volumio]()
* Khadas SD images
  * [VIM1](https://dl.khadas.com/Firmware/VIM1/Ubuntu/SD_USB/)
  * [VIM2](https://dl.khadas.com/Firmware/VIM2/Ubuntu/SD_USB/)
  * [VIM3](https://dl.khadas.com/Firmware/VIM3/Ubuntu/SD_USB/)

This tutorial is about how to boot these images.

## Install Image to SD/USB Storage

Please check [Install System on SD/USB Storage](InstallOsIntoSdusb.html).

## Select the Appropriate DTB

### For Armbian, LibreELEC, Manjaro
You need to select the appropriate DTB file.

* Navigate to your SD card's / Thumbdrive's `BOOT` partition, and open the folder labelled `dtb`.

* Find the correct .dtb filename in the folder `/dtb`. Examples:
  * VIM1: `/dtb/meson-gxl-s905x-khadas-vim.dtb`
  * VIM2: `/dtb/meson-gxm-khadas-vim2.dtb`
  * VIM3: `/dtb/meson-g12b-a311d-khadas-vim3.dtb`
  * VIM3L: `/dtb/meson-sm1-khadas-vim3l.dtb`
* Edit `FDT` in `/extlinux/extlinux.conf` and `dtb_name=` in `uEnv.ini` with the correct dtb filename.

### For CoreELEC
* Find the appropriate `.dtb` file in `COREELEC` partition `dtb` folder:
  * VIM1: Copy `gxl_p212_2g_kvim.dtb` to `COREELEC` partition, and rename it to `dtb.img`.
  * VIM2: Copy `gxm_kvim2.dtb` to `COREELEC` partition, and rename it to `dtb.img`.
  * VIM3: Copy `g12b_a311d_khadas_vim3` to `COREELEC` partition, and rename it to `dtb.img`.

### For Volumio
* Find the appropriate `.dtb` file in `BOOT` partition `dtb` folder:
  * VIM1: Copy `kvim.dtb`, `kvim_linux.dtb` or `meson-gxl-s905x-khadas-vim.dtb` to `BOOT` partition, and rename it to `dtb.img`.
  * VIM2: Copy `kvim2.dtb`, `kvim2_linux.dtb` or `meson-gxm-khadas-vim2.dtb` to `BOOT` partition, and rename it to `dtb.img`.
  * VIM3: Copy `kvim3_linux.dtb` or `kvim3l_linux.dtb` to `BOOT` partition, and rename it to `dtb.img`.

### For Khadas SD/USB Images

No need to setup the dtb file, just skip this step.

## Boot from SD/USB Storage
There are several ways to boot (activate multi-boot) from the SD card / Thumbdrive:

* Via [Keys mode (Side-Buttons)](BootIntoUpgradeMode.html) - the easiest and fastest way

* Via Android

  * Enter `Settings->About Device->System->Updates`.
  * Click select and choose `aml_autosript.zip`.
  * Click update, then the system will reboot and boot from the external media image.

{% note warn WARNING %}

Don't use your PC as the USB-Host to supply the electrical power, otherwise it will fail to activate Multi-Boot!

{% endnote %}

{% note warn NOTICE %}

If any other OS than Android, Armbian or LibreELEC has been installed to eMMC and you want to install either Armbian or LibreELEC to eMMC, the eMMC has to be completely wiped with `dd` before latest Ubuntu is burned to eMMC by following [Install OS into eMMC](InstallOsIntoEmmc.html).

{% endnote %}

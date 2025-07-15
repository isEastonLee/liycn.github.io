---
date:
   created: 2025-03-17
readtime: 30
authors:
  - lee
---

在网上能找到许多关于 `HackRF One` 的安装教程，通常可以归为两种方式：  
1. **直接克隆项目进行 cmake 编译**  
2. **下载发行版的压缩包**  

两种方法我都尝试过，不夸张地说，直接下载发行包的方式更加简单高效。因此，本文将重点讨论使用发行包的方式。毕竟，官方都已整理好了发行包，直接安装显然更省时省力。  

事实上，我在尝试克隆编译的过程中并未成功，主要原因是：在拔掉 USB 或者按下 reset 按钮后，设备往往无法重新连接 USB，导致使用不便。  

<!-- more -->

## 安装环境检查

在终端中输入以下命令，查看 HackRF One 的驱动与固件信息：

```bash
hackrf_info
```

如果发现 hackrf_info version 和 libhackrf version 都显示为 “未知”，这通常意味着系统安装的驱动版本与设备固件版本不匹配。此时需要进行驱动升级。

> 提示：在升级前，建议先确认当前固件版本与驱动版本是否兼容，避免因版本冲突引发问题。

![1.png](/images/blog/Bluetooth/HackRF One/1.jpg "网图，因为我的已经没有了")

|环境内容|版本|
|:-|:-|
|系统|Ubuntu 20.04 (在 Windows 11 中的 VMware 虚拟机)|
|HackRF One|初始版本 2018（存在兼容性问题）|
|仓库地址|[hackrf](https://github.com/greatscottgadgets/hackrf){target="_blank"}|
|目标固件版本|2021.03.1（根据设备版本选择合适版本）|

***

## 环境安装

在安装 HackRF One 之前，需要安装以下相关的软件包和依赖项：

```bash
sudo apt-get install gnuradio hackrf libhackrf-dev gqrx-sdr rtl-sdr gr-osmosdr osmo-sdr libusb-1.0
```

确保所有包都能正常安装，避免因缺失依赖导致安装失败。

## 下载发行版安装包

推荐直接下载官方发布的稳定版本。以下是 2021.03.1 版本的下载链接：

[hackrf release 2021.03.1](https://github.com/greatscottgadgets/hackrf/releases/download/v2021.03.1/hackrf-2021.03.1.tar.xz)

若需要其他版本，可以在 [GitHub 官方仓库](https://github.com/greatscottgadgets/hackrf/releases){target="_blank"} 中选择合适版本。

## 解压与安装

1. 解压发行包文件：

```bash
xz -d hackrf-2021.03.1.tar.xz
tar xvf hackrf-2021.03.1.tar
```

2. 创建 `build` 目录并编译：

```bash
cd hackrf-2021.03.1/host
mkdir build && cd build
```

3. 使用 `cmake` 进行配置与编译：

```bash
cmake ../ -DINSTALL_UDEV_RULES=ON
make
sudo make install
sudo ldconfig
```
> 注意：如果出现编译错误，建议检查 cmake 版本和依赖包是否完整。

## 固件升级

### 更新 Flash 固件

若 Firmware Version 版本过旧，需要进行 Flash 固件更新，在 firmware-bin 目录下执行以下命令：

```bash
hackrf_spiflash -w hackrf_one_usb.bin
```

### 更新 CPLD（仅适用于 `2018.01.1` 版本以上）

从 2021 版本开始，CPLD 已包含在固件中，并在加载固件时自动更新，因此通常无需单独更新。但若你的固件版本较旧，仍需手动更新 CPLD：

```bash
hackrf_cpldjtag -x hackrf_cpld_default.xsvf
```

## 安装结果验证

在终端中输入以下命令，确认设备信息是否正确更新：

```bash
hackrf_info
```

若信息显示完整且版本号正确，说明设备已成功配置和更新。

### 最终效果展示

![2.png](/images/blog/Bluetooth/HackRF One/2.png)
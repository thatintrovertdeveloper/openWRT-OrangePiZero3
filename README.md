<div align="center">
<img width="768" src="https://cdn.jsdelivr.net/gh/haiibo/OpenWrt/images/openwrt.png"/>
<h1>OpenWrt — Orange Pi Zero3 Personal Use</h1>

</div>

## Project Description [![](https://img.shields.io/badge/-Project_Basic_Introduction-FFFFFF.svg)](#Project_Description)

- Firmware components: [![Lean](https://img.shields.io/badge/Lede-Lean-ff69b4.svg?style=flat&logo=appveyor)](https://github.com/coolsnowwolf/lede) [![P3TERX](https://img.shields.io/badge/OpenWrt-P3TERX-blueviolet.svg?style=flat&logo=appveyor)](https://github.com/P3TERX/Actions-OpenWrt) [![Flippy](https://img.shields.io/badge/Package-Flippy-orange.svg?style=flat&logo=appveyor)](https://github.com/unifreq/openwrt_packit) [![Haiibo](https://img.shields.io/badge/Build-Haiibo-32C955.svg?style=flat&logo=appveyor)](https://github.com/haiibo/OpenWrt)
- The project uses Github Actions to fetch OpenWrt source code from [Lean](https://github.com/coolsnowwolf/lede) repository for cloud compilation.
- Default management address of the firmware: `192.168.1.1`, Default user: `root`, Default password: `password`.

## Firmware Features [![](https://img.shields.io/badge/-Firmware_Features-FFFFFF.svg)](#Firmware_Features)

1. The firmware is automatically compiled daily to ensure the latest experience.
2. Integrates drivers for common wired, wireless, and 3G / 4G network cards.

## Plugin Preview [![](https://img.shields.io/badge/-Firmware_Plugins_and_Features_Preview-FFFFFF.svg)](#Plugin_Preview)

<details>
<summary><b>&nbsp;Orange Pi Zero3 Plugin Preview</b></summary>
<br/>
<img src="https://raw.githubusercontent.com/jym66/openWRT-OrangePiZero3/main/images/openwrt1.png"/>
</details>

## Custom Firmware [![](https://img.shields.io/badge/-Project_Compilation_Tutorial-FFFFFF.svg)](#Custom_Firmware)

1. First, log in to your Github account and then fork this project into your own Github repository.
2. Modify the files in the `configs` directory to add or remove plugins, or upload your own `xx.config` configuration file.
3. For plugin names and features, please refer to the post from the user on Enshan forum: [Applications Adding Plugin Instructions](https://www.right.com.cn/forum/thread-3682029-1-1.html).
4. To modify the default IP, add or remove plugin packages, and make other changes, please edit the `diy-script.sh` file.
5. Add or modify the `xx.yml` file, then go to `Actions` and run the workflow you want to compile.
6. Compilation takes approximately 3-5 hours. Once completed, you can download the firmware from the corresponding tag on the repository's [Releases](https://github.com/haiibo/OpenWrt/releases) page.

<details>
<summary><b>&nbsp;If you find modifying config files troublesome, you can try extracting locally here</b></summary>

1. First, install a Linux system, preferably Debian 11 or Ubuntu LTS.

2. Install the build dependencies:

   ```bash
   sudo apt update -y
   sudo apt full-upgrade -y
   sudo apt install -y ack antlr3 asciidoc autoconf automake autopoint binutils bison build-essential \
   bzip2 ccache cmake cpio curl device-tree-compiler fastjar flex gawk gettext gcc-multilib g++-multilib \
   git gperf haveged help2man intltool libc6-dev-i386 libelf-dev libglib2.0-dev libgmp3-dev libltdl-dev \
   libmpc-dev libmpfr-dev libncurses5-dev libncursesw5-dev libreadline-dev libssl-dev libtool lrzsz \
   mkisofs msmtp nano ninja-build p7zip p7zip-full patch pkgconf python2.7 python3 python3-pyelftools \
   libpython3-dev qemu-utils rsync scons squashfs-tools subversion swig texinfo uglifyjs upx-ucl unzip \
   vim wget xmlto xxd zlib1g-dev
   ```

3. Download the source code, update feeds, and install locally:

   ```bash
   git clone https://github.com/coolsnowwolf/lede
   cd lede
   ./scripts/feeds update -a
   ./scripts/feeds install -a
   ```

4. Copy all contents of the `diy-script.sh` file into the command line to add custom plugins and settings.

5. Run `make menuconfig` in the command line to select the configuration. After choosing, export the diff to a `seed.config` file:

   ```bash
   make defconfig
   ./scripts/diffconfig.sh > seed.config
   ```

6. Use the command `cat seed.config` to view this file, or open it with a text editor.

7. Copy all contents from the `seed.config` file and overwrite the corresponding file in the `configs` directory.

   **If you don't understand the compilation interface, you can refer to this YouTube video: [Soft Router Firmware OpenWrt Compilation Interface Setup](https://www.youtube.com/watch?v=jEE_J6-4E3Y&list=WL&index=7)**

</details>

## Special Notes [![](https://img.shields.io/badge/-Personal_Disclaimer-FFFFFF.svg)](#Special_Notes)

- **Due to limited time, no technical support or tutorials will be provided. No guarantee of a completely bug-free experience!**
- **I am not responsible for any theoretical or actual losses caused by the use of this firmware!**
- **This firmware is prohibited for commercial use. Please strictly comply with national internet usage laws and regulations!**

## Acknowledgements [![](https://img.shields.io/badge/-Thanks_to_All_Contributors-FFFFFF.svg)](#Acknowledgements)

|               [ImmortalWrt](https://github.com/immortalwrt)               |              [coolsnowwolf](https://github.com/coolsnowwolf)              |                    [P3TERX](https://github.com/P3TERX)                    |                   [Flippy](https://github.com/unifreq)                    |
| :-----------------------------------------------------------------------: | :-----------------------------------------------------------------------: | :-----------------------------------------------------------------------: | :-----------------------------------------------------------------------: |
| <img width="100" src="https://avatars.githubusercontent.com/u/53193414"/> | <img width="100" src="https://avatars.githubusercontent.com/u/31687149"/> | <img width="100" src="https://avatars.githubusercontent.com/u/25927179"/> | <img width="100" src="https://avatars.githubusercontent.com/u/39355261"/> |
|                     [Ophub](https://github.com/ophub)                     |                  [SuLingGG](https://github.com/SuLingGG)                  |                 [QiuSimons](https://github.com/QiuSimons)                 |             [IvanSolis1989](https://github.com/IvanSolis1989)             |
| <img width="100" src="https://avatars.githubusercontent.com/u/68696949"/> | <img width="100" src="https://avatars.githubusercontent.com/u/22287562"/> | <img width="100" src="https://avatars.githubusercontent.com/u/45143996"/> | <img width="100" src="https://avatars.githubusercontent.com/u/44228691"/> |

<a href="#readme">
<img src="https://img.shields.io/badge/-Back_to_Top-FFFFFF.svg" title="Back to Top" align="right"/>
</a>

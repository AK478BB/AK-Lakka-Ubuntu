Lakka和Ubuntu的SD卡文件包（2024.8.30）

https://pan.baidu.com/s/14S-4dqDad7zv7S0czbm1dA?pwd=1b6d

Lakka版本Lakka-Switch.aarch64-5.x-20240723-e2c1b74

Ubuntu版本theofficialgman-ubuntu-unity-noble-5.1.2-2024-05-20

【说明】
（1）解压缩可直接覆盖到任何的大气层整合包，但要确认Hekate支持L4t，因为lakka和ubuntu都是独立系统，所以能否运行和大气层的版本、Switch系统的版本均无关，只和Hekate有关，确认Hekate是6.0.1/6.0.2及以后版本。
因为这样Switch所有型号主机都能玩Lakka或Ubuntu，Joycon建议用原装的。

玩ubuntu要预先在Hekate中给sd卡做8G隐藏分区，建议先分区完成后再解压缩覆盖到sd卡，建立隐藏分区后sd卡剩余分区默认fat32格式。

（2）Hekate开机，more configs中找到新的引导

Lakka-Erista，是AK大气层原来设定的旧lakka模拟器。它只支持软破或补丁机，但能兼容exfat格式的sd卡

Lakka-l4t：是新的lakka模拟器，兼容mariko/oled，目前新lakka只能支持fat32格式的sd卡

ubuntu-l4t：是新的ubuntu系统，兼容mariko/oled，目前新ubuntu只能支持fat32格式的sd卡

（3）Mariko想玩lakka或ubuntu必须先升级芯片固件的sdloader

不管是hwfly国产芯片，还是TX原厂芯片已刷了小飞船固件，都要先升级固件的sdloader。

而且每次正版系统升级后也要重新刷一次sdloader，是hwfly工具箱升级，所以免拆机，挺安全的。

https://github.com/hwfly-nx/firmware/releases

下最新的hwfly-toolbox.bin到sd卡bootloader/payloads/

下最新的sdloader.enc到sd卡根目录

在Hekate中payloads-hwfly-toolbox.bin，进入找到sdloader，选择update完成。

hwfly工具箱的操作是音量加减为上下键，电源键是确定键，类似lockpick工具。

【lakka和ubuntu教程】

（1）Lakka-Erista

这是旧的通过coreboot.rom引导的Lakka模拟器系统，有大佬编译支持了exfat的coreboot.rom。只能支持软破和补丁硬破，lakka模拟器的安装只是复制一个lakka文件夹，所以可以直接新加。

lakka路径是一样的，只能和lakka-l4t两选一，保留或删除另一个都可以。

（2）Lakka-l4t

https://lakka.tv/get/linux/switch/

Hekate启动已配置好，在Hekate中先在nyx设置中备份原装蓝牙手柄信息，只要下载和复制lakka文件夹到根目录后就可以进入lakka，免安装，只支持fat32的sd卡。

（3）ubuntu-l4t

https://download.switchroot.org/

Hekate启动已配置好，在Hekate中先在nyx设置中备份原装蓝牙手柄信息，然后进行分区，新建linux的8g隐藏分区。最后usb连电脑，复制Switchroot文件夹到sd卡的根目录，在Hekate中继续下一步安装linux，安装完毕就可以删除安装包后进入ubuntu

（4）一张SD卡可以实现多个系统的共存，开机Hekate启动后选择或重启后切换。

真实系统[nintendo]+虚拟系统[emummc]+ubuntu系统[switchroot]+lakka模拟器[lakka]

第一步先做ubuntu系统，卡会格式化为fat32

如果想还原备份到电脑上的虚拟系统文件（原exfat的sd卡）。

emummc/sd00/emmc，可以借助nxnandmanager还原到sd卡，自动分割为4G，

emummc/sd00/nintendo/文件夹再复制到对应路径，里面是不会有大于4G的单个文件

完成后虚拟系统里的游戏和存档都不会丢失

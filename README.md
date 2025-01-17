# [fancyss - 科学上网](https://hq450.github.io/fancyss/)

> Fancyss is a project providing tools to across the GFW on asuswrt/merlin/openwrt based router with software center. 
>
> 此项目提供用于asuswrt/merlin/openwrt为基础的，带软件中心固件路由器的科学上网。

---

**提示1：** 如果提示检测到离线安装包名有非法关键词，开启路由器的SSH功能，登录并输入以下命令后，再进行离线安装。(arm380/X7.x版本固件需要请将软件中心更新到1.4.8及以上)

```bash
sed -i 's/\tdetect_package/\t# detect_package/g' /koolshare/scripts/ks_tar_install.sh
```

**提示2：** 如果更新了梅林386改版固件，状态出现双:x:的，请使用离线装功能覆盖安装一次科学上网插件。

---

## 机型/固件支持（表格版）

> 下面的表格列出了各个不同版本fancyss对固件/平台/架构等的支持情况，以及不同fancyss对一些功能/特性的支持情况，对应的文字说明请见下文。

|               |                         fancyss_hnd                          | fancyss_qca        |                        fancyss_arm384                        |                         fancyss_arm                          |                        fancyss_mipsel                        |                         fancyss_x64                          |
| :-----------: | :----------------------------------------------------------: | ------------------ | :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: |
|   固件来源    |                          koolshare                           | koolshare          |                          koolshare                           |                          koolshare                           |                          koolshare                           |                          koolshare                           |
|     固件      |                      梅林改版/华硕官改                       | 华硕官改           |                         梅林384改版                          |                         梅林380改版                          |                           梅林改版                           |                        LEDE by fw867                         |
|     架构      |                         armv8/armv7                          | armv8              |                            armv7                             |                            armv7                             |                            mipsel                            |                             x64                              |
|     平台      |                     hnd/axhnd/axhnd.675x                     | qca-ipq806x        |                             arm                              |                             arm                              |                            mipsel                            |                             x64                              |
|   linux内核   |                            4.1.xx                            | 4.4.0-116          |                           2.6.36.4                           |                           2.6.36.4                           |                             2.6                              |                             很新                             |
|      CPU      |                       bcm490x/bcm675x                        | ipq8074            |                          bcm4708/9                           |                          bcm4708/9                           |                           bcm4706                            |                          x64架构CPU                          |
|   维护状态    |                          缓慢维护中                          | 缓慢维护中         |                          缓慢维护中                          |                         **停止维护**                         |                         **停止维护**                         |                         **备份留存**                         |
|   最新版本    |                          **1.9.6**                           | 2.0.0              |                          **1.0.4**                           |                          **4.2.2**                           |                         **3.0.4？**                          |                          **2.2.2**                           |
|   插件名称    |                           科学上网                           | 科学上网           |                           科学上网                           |                           科学上网                           |                           科学上网                           |                            koolss                            |
|   节点管理    |                      :heavy_check_mark:                      | :heavy_check_mark: |                      :heavy_check_mark:                      |                      :heavy_check_mark:                      |                      :heavy_check_mark:                      |                      :heavy_check_mark:                      |
|    ss支持     |                      :heavy_check_mark:                      | :heavy_check_mark: |                      :heavy_check_mark:                      |                      :heavy_check_mark:                      |                      :heavy_check_mark:                      |                      :heavy_check_mark:                      |
|    ssr支持    |                      :heavy_check_mark:                      | :heavy_check_mark: |                      :heavy_check_mark:                      |                      :heavy_check_mark:                      |                      :heavy_check_mark:                      |                      :heavy_check_mark:                      |
|   游戏模式    |                      :heavy_check_mark:                      | :heavy_check_mark: |                      :heavy_check_mark:                      |                      :heavy_check_mark:                      |                             :x:                              |                      :heavy_check_mark:                      |
|   节点订阅    |                      :heavy_check_mark:                      | :heavy_check_mark: |                      :heavy_check_mark:                      |                      :heavy_check_mark:                      |                             :x:                              |                      :heavy_check_mark:                      |
|   回国模式    |                      :heavy_check_mark:                      | :heavy_check_mark: |                      :heavy_check_mark:                      |                      :heavy_check_mark:                      |                             :x:                              |                             :x:                              |
|   v2ray支持   |                      :heavy_check_mark:                      | :heavy_check_mark: |                      :heavy_check_mark:                      |                      :heavy_check_mark:                      |                             :x:                              |                             :x:                              |
|   koolgame    |                      :heavy_check_mark:                      | :heavy_check_mark: |                      :heavy_check_mark:                      |                      :heavy_check_mark:                      |                             :x:                              |                             :x:                              |
|   节点排序    |                      :heavy_check_mark:                      | :heavy_check_mark: |                      :heavy_check_mark:                      |                             :x:                              |                             :x:                              |                      :heavy_check_mark:                      |
|   故障转移    |                      :heavy_check_mark:                      | :heavy_check_mark: |                      :heavy_check_mark:                      |                             :x:                              |                             :x:                              |                             :x:                              |
| v2ray-plugin  |                      :heavy_check_mark:                      | :heavy_check_mark: |                      :heavy_check_mark:                      |                      :heavy_check_mark:                      |                             :x:                              |                             :x:                              |
|   多核支持    |                      :heavy_check_mark:                      | :heavy_check_mark: |                             :x:                              |                             :x:                              |                             :x:                              |                             :x:                              |
| tcp_fast_open |                      :heavy_check_mark:                      | :heavy_check_mark: |                             :x:                              |                             :x:                              |                             :x:                              |                             :x:                              |
|   更新日志    | [Changelog.txt](https://github.com/hq450/fancyss/blob/master/fancyss_hnd/Changelog.txt) |                    | [Changelog.txt](https://github.com/hq450/fancyss/blob/master/fancyss_arm384/Changelog.txt) | [Changelog.txt](https://github.com/hq450/fancyss/blob/master/fancyss_arm/Changelog.txt) |                             null                             | [Changelog.txt](https://github.com/hq450/fancyss/blob/master/fancyss_X64/Changelog.txt) |
|  离线包下载   | [fancyss_hnd](https://github.com/hq450/fancyss_history_package/tree/master/fancyss_hnd) |                    | [fancyss_arm384](https://github.com/hq450/fancyss_history_package/tree/master/fancyss_arm384) | [fancyss_arm](https://github.com/hq450/fancyss_history_package/tree/master/fancyss_arm) | [fancyss_mipsel](https://github.com/hq450/fancyss_history_package/tree/master/fancyss_mipsel) | [fancyss_x64](https://github.com/hq450/fancyss_history_package/tree/master/fancyss_X64) |



## 机型/固件支持（文字版）

### [fancyss_hnd](https://github.com/hq450/fancyss/tree/master/fancyss_hnd)

> **fancyss_hnd**离线安装包仅能在koolshare 梅林/官改 hnd/axhnd/axhnd.675x平台机器上使用！具体支持机型如下：

#### fancyss_hnd 支持机型/固件：

| 机型/固件下载    | 类型   | 平台           | CPU     | 架构  | 支持版本 | 皮肤            |
| ---------------- | ------ | -------------- | ------- | ----- | -------- | --------------- |
| RT-AC86U         | 梅林改 | hnd            | BCM4906 | ARMV8 | 全部     | asuswrt         |
| RT-AC86U         | 官改   | hnd            | BCM4906 | ARMV8 | 全部     | rog/asuswrt[^1] |
| GT-AC2900        | 梅林改 | hnd            | BCM4906 | ARMV8 | ≥ 1.9.1  | asuswrt [^2]    |
| GT-AC2900        | 官改   | hnd            | BCM4906 | ARMV8 | ≥ 1.9.1  | rog             |
| GT-AC5300        | 官改   | hnd            | BCM4908 | ARMV8 | 全部     | rog             |
| RT-AX88U         | 梅林改 | axhnd          | BCM4908 | ARMV8 | 全部     | asuswrt         |
| RAX80            | 梅林改 | axhnd          | BCM4908 | ARMV8 | 全部     | asuswrt         |
| GT-AX11000       | 官改   | axhnd          | BCM4908 | ARMV8 | 全部     | rog             |
| RT-AX92U         | 官改   | axhnd          | BCM4906 | ARMV8 | ≥ 1.9.1  | asuswrt         |
| TUF-AX3000       | 官改   | axhnd.675x     | BCM6750 | ARMV7 | ≥ 1.8.3  | tuf             |
| TUF-AX5400       | 梅林改 | axhnd.675x     | BCM6750 | ARMV7 | ≥ 1.9.7  | tuf             |
| TUF-AX5400       | 官改   | axhnd.675x     | BCM6750 | ARMV7 | ≥ 1.9.7  | tuf             |
| RT-AX58U         | 梅林改 | axhnd.675x     | BCM6750 | ARMV7 | ≥ 1.8.4  | asuswrt         |
| RAX50            | 梅林改 | axhnd.675x     | BCM6750 | ARMV7 | ≥ 1.8.4  | asuswrt         |
| RT-AX82U         | 官改   | axhnd.675x     | BCM6750 | ARMV7 | ≥ 1.8.4  | asuswrt         |
| RT-AX82U         | 梅林改 | axhnd.675x     | BCM6750 | ARMV7 | ≥ 1.9.1  | asuswrt         |
| ZenWiFi_XT8      | 官改   | axhnd.675x     | BCM6755 | ARMV7 | ≥ 1.8.7  | asuswrt         |
| ZenWiFi_XT8      | 梅林改 | axhnd.675x     | BCM6755 | ARMV7 | ≥ 1.9.1  | asuswrt         |
| ZenWiFi_XD4      | 官改   | axhnd.675x     | BCM6755 | ARMV7 | ≥ 1.8.8  | asuswrt         |
| RT-AX56U_V2      | 官改   | axhnd.675x     | BCM6755 | ARMV7 | ≥ 1.9.0  | asuswrt         |
| RT-AX56U         | 梅林改 | axhnd.675x     | BCM6755 | ARMV7 | ≥ 1.9.1  | asuswrt         |
| RT-AX68U         | 官改   | p1axhnd.675x   | BCM4906 | ARMV8 | ≥ 1.9.1  | asuswrt         |
| RT-AX68U         | 梅林改 | p1axhnd.675x   | BCM4906 | ARMV8 | ≥ 1.9.1  | asuswrt         |
| RT-AX86U         | 官改   | p1axhnd.675x   | BCM4908 | ARMV8 | ≥ 1.8.3  | asuswrt         |
| RT-AX86U         | 梅林改 | p1axhnd.675x   | BCM4908 | ARMV8 | ≥ 1.9.1  | asuswrt         |
| GT-AXE11000      | 梅林改 | p1axhnd.675x   | BCM4908 | ARMV8 | ≥ 1.9.1  | asuswrt         |
| GT-AX6000        | 官改   | 5.04axhnd.675x | BCM4912 | ARMV8 | ≥ 1.9.6  | rog             |
| GT-AX6000        | 梅林改 | 5.04axhnd.675x | BCM4912 | ARMV8 | ≥ 1.9.8  | asuswrt         |
| ZenWiFi_Pro_XT12 | 官改   | 5.04axhnd.675x | BCM4912 | ARMV8 | ≥ 1.9.6  | asuswrt         |

#### 注意：

* fancyss_hnd目前仅支持以上改版固件机型，其它架构/平台固件，原版固件均不能使用fancyss_hnd！
* 相关机型的梅林改/官改固件下载请前往：[https://www.koolcenter.com/](https://www.koolcenter.com/)
* 使用fancyss_hnd科学上网插件，强烈建议使用chrome或者chrouium内核的浏览器！以保证最佳兼容性！
* 强烈建议在`最新版本的固件`和`最新版本软件中心`上使用fancyss_hnd！
* GT-AC2900/GT-AC5300/GT-AX11000/GT-AX6000官改使用ROG皮肤，插件安装会自动识别机型并安装对应皮肤版本。
* TUF-AX3000/TUF-AX5400官改固件使用的是TUF橙色皮肤，插件安装会自动识别机型并安装对应皮肤版本。
* TUF-AX5400梅林改版固件使用的是TUF橙色皮肤，插件安装会自动识别机型并安装对应皮肤版本。
* 一些机型的联名版如GT-AX11000使命召唤黑色行动版/海妖版，RT-AX86U高达版/鬼灭之刃版，RT-AX82U高达版，RT-AX88U高达版本等各种联名版均是默认支持的。
* 部分机型只有达到特定版本后才能使用，386固件需要fancyss_hnd ≥ 1.9.1版本才能使用

[^1]: RT-AC86U从384_81918_koolshare固件版本开始，使用的是asuswrt风格ui，而不是rog风格。

[^2]: RT-AC86U从384_81918_koolshare固件版本开始，使用的是asuswrt风格ui，而不是rog风格。

#### 相关链接：

* fancyss_hnd离线包：[https://github.com/hq450/fancyss_history_package/tree/master/fancyss_hnd](https://github.com/hq450/fancyss_history_package/tree/master/fancyss_hnd)
* fancyss_hnd更新日志：https://github.com/hq450/fancyss/blob/master/fancyss_hnd/Changelog.txt
* fancyss_hnd机型的固件下载地址：[http://koolshare.cn/forum-96-1.html](http://koolshare.cn/forum-96-1.html)

----

### [fancyss_qca](https://github.com/hq450/fancyss/tree/master/fancyss_qca)

> fancyss_qca适用于`koolshare 官改 qca-ipq806x`固件平台，目前仅支持华硕高通机型：RT-AX89X。

#### fancyss_qca  支持机型/固件：


| 机型/固件下载                                           | 类型 | CPU/SOC | 平台        | 架构    | 内核   | 皮肤    |
| ------------------------------------------------------- | ---- | ------- | ----------- | ------- | ------ | ------- |
| [RT-AC89X](https://koolshare.cn/thread-188090-1-1.html) | 官改 | IPQ8074 | qca-ipq806x | ARMV7/8 | 4.4.60 | asuswrt |


#### 注意：

* 其它架构/平台固件不能使用fancyss_qca！
* 使用本插件建议使用chrome或者chrome内核的浏览器！
* 强烈建议在`最新版本的固件`和`最新版本软件中心`上使用fancyss_qca！

#### 相关链接：

* fancyss_qca离线包：[https://github.com/hq450/fancyss_history_package/tree/master/fancyss_qca](https://github.com/hq450/fancyss_history_package/tree/master/fancyss_qca)
* fancyss_qca更新日志：https://github.com/hq450/fancyss/blob/master/fancyss_qca/Changelog.txt
* fancyss_hnd机型的固件下载地址：[http://koolshare.cn/forum-96-1.html](http://koolshare.cn/forum-96-1.html)

----

### [fancyss_arm384](https://github.com/hq450/fancyss/tree/master/fancyss_arm)

> **fancyss_arm384**离线安装包仅能在koolshare 梅林 arm 384/386平台，且linux内核为2.6.36.4的armv7架构的机器上使用！

**fancyss_arm384**支持机型（需刷koolshare梅林**384/386**改版固件，如384_18、386_1）：

* 华硕系列：`RT-AC68U` `RT-AC66U-B1` `RT-AC1900P` `RT-AC87U` `RT-AC88U` `RT-AC3100` `RT-AC3200` `RT-AC5300`

#### 注意：

* 其它架构/平台固件不能使用fancyss_arm384！
* **386固件版本的机器只能使用≥ 1.0.5版本的fancyss_arm384！**
* 使用本插件建议使用chrome或者chrome内核的浏览器！
* 强烈建议在最新版本的固件和最新版本软件中心上使用fancyss_arm384！

#### 相关链接：

* arm384机型的科学上网离线包：[https://github.com/hq450/fancyss_history_package/tree/master/fancyss_arm384](https://github.com/hq450/fancyss_history_package/tree/master/fancyss_arm384)
* arm384机型的科学上网更新日志：https://github.com/hq450/fancyss/blob/master/fancyss_arm384/Changelog.txt
* arm384机型的固件下载地址：[https://koolshare.cn/thread-164857-1-1.html](https://koolshare.cn/thread-164857-1-1.html)

----

### [fancyss_arm](https://github.com/hq450/fancyss/tree/master/fancyss_arm)（停止维护）

> **fancyss_arm 停止维护通知：**
>
> 2019年12月10日 
>
> -- by hq450
>
> 因为fancyss_arm支持的固件较旧（最高380 X7.9.1），软件中心API较旧（1.0代），并且维护者持有的armv7机型（RT-AC5300）的固件已经升级到koolshare 384版本，加上代码差异时间问题，很难继续维持下去。所以arm380平台上的科学上网插件停止维护，最终版本将停留在4.2.2。
>
> 如果你持有华硕armv7机型（`RT-AC68U` `RT-AC66U-B1` `RT-AC1900P` `RT-AC87U` `RT-AC88U` `RT-AC3100` `RT-AC3200` `RT-AC5300`），那么你可以将你的固件更新至koolshare 384版本（[固件下载地址](https://koolshare.cn/thread-164857-1-1.html)）后使用fancyss_arm384，目前fancyss_arm384处于维护状态，且功能上更加新。
>
> 如果你持有的是网件、linksys等armv7机型，那么非常遗憾，因为你的机器固件最高只能支持到koolshare arm380 X7.9.1，所以你只能使用已经停止维护的fancyss_arm，最终版本为4.2.2，不过你仍然可以获得v2ray二进制和规则的更新。如果你在其他地方看见有人发布高于此版本的离线包，请谨慎使用，因为这很可能不是本项目发布的。

> **fancyss_arm**离线安装包仅能在koolshare 梅林 arm 380平台，且linux内核为2.6.36.4的armv7架构的机器上使用！

**fancyss_arm**支持机型（需刷koolshare梅林**380**改版固件，最新版本：X7.9.1）：

* 华硕系列：`RT-AC56U` `RT-AC68U` `RT-AC66U-B1` `RT-AC1900P` `RT-AC87U` `RT-AC88U` `RT-AC3100` `RT-AC3200` `RT-AC5300`
* 网件系列：`R6300V2` `R6400` `R6900` `R7000` `R8000` `R8500`
* linksys EA系列：`EA6200` `EA6400` `EA6500v2` `EA6700` `EA6900`
* 华为：`ws880`

#### 注意：

* 其它架构/平台固件不能使用fancyss_arm！
* 使用本插件建议使用chrome或者chrome内核的浏览器！
* 强烈建议在最新版本的固件和最新版本软件中心上使用fancyss_arm！
* fancyss_arm仅支持版本号≥X7.2的固件，订阅功能需要版本号≥X7.7（最新版本固件为X7.9.1）

#### 相关链接：

* arm机型的科学上网离线包：[https://github.com/hq450/fancyss_history_package/tree/master/fancyss_arm](https://github.com/hq450/fancyss_history_package/tree/master/fancyss_arm)
* arm机型的科学上网更新日志：https://github.com/hq450/fancyss/blob/master/fancyss_arm/Changelog.txt
* arm机型的固件下载地址：[http://koolshare.cn/forum-96-1.html](http://koolshare.cn/forum-96-1.html)

----

### [fancyss_mipsel](https://github.com/hq450/fancyss/tree/master/fancyss_mipsel) （停止维护）

> 适用于merlin koolshare mipsel架构机型的改版固件，由于mipsel架构老旧且性能较低，此架构机型的科学上网插件已经不再维护，最后的版本是3.0.4，此处作为仓库搬迁后的备份留存。

**fancyss_mipsel**支持机型（需刷梅林koolshare改版固件）：

* 华硕系列：`RT-N66U` `RT-AC66U（非RT-AC66U-B1）`

#### 相关链接：

* mipsel机型的科学上网离线包：[https://github.com/hq450/fancyss_history_package/tree/master/fancyss_mipsel](https://github.com/hq450/fancyss_history_package/tree/master/fancyss_mipsel)
* mipsel机型的固件下载地址：[http://koolshare.cn/forum-96-1.html](http://koolshare.cn/forum-96-1.html)

----

### [fancyss_X64](https://github.com/hq450/fancyss/tree/master/fancyss_X64) （备份留存）

> 适用于koolshare OpenWRT/LEDE X64 带酷软的固件，由于该固件酷软下架了koolss插件，本项目将其收入。

#### 相关链接：
* koolshare OpenWRT/LEDE X64机型的科学上网离线包：[https://github.com/hq450/fancyss_history_package/tree/master/fancyss_X64](https://github.com/hq450/fancyss_history_package/tree/master/fancyss_X64)



* [msinfo32](https://support.microsoft.com/zh-cn/topic/microsoft-%E7%B3%BB%E7%BB%9F%E4%BF%A1%E6%81%AF-msinfo32-exe-%E5%B7%A5%E5%85%B7%E7%9A%84%E8%AF%B4%E6%98%8E-10d335d8-5834-90b4-8452-42c58e61f9fc)

## 阿里旺旺

??? note "[qt 技术支持](https://shop63228210.taobao.com/shop/view_shop.htm?shop_id=63228210)"

    * "我想在QT上用libusb库写一个与USB通讯的程序，打印USB的PID、VID，然后测试传送、接受功能，测试传输速度"
    * "[我现在只要把网上这个例子调通](http://blog.csdn.net/u010684585/article/details/51121104)，编译能运行就行"
    * "就比如简单的数据接收，这些你下的libusb都有示例"
    * "加我qq吧，给你演示 472506162"

    ??? info "少头文件"

        ![][少头文件]

??? note "[韦东山](https://100ask.taobao.com/shop/view_shop.htm?shop_id=60147702)"

    ??? info "加密视频使用方法"

        1. [百度盘下载视频](https://v.qq.com/x/page/p0532n6v95k.html)
        2. [下载播放器huplayer](https://www.drm-x.com)
        3. huplayer打开 点击文件，快速打开文件 找到加密视频输入用户名、密码

??? note "冷冻盒"

    这个问题是因为打包时候用透明胶带裹太紧了，导致盖子稍稍有点挤压到了，可以调整的。用50-60度热水浸泡盖子5-10分钟  然后放在平面的桌子上，用盒身压在盖子上面冷却即可。您试试看~ 

??? note "[双系统 ubuntu](https://shop116224857.taobao.com/shop/view_shop.htm?shop_id=116224857)"

    ??? question "装ubuntu必须要u盘吗"

        有的不用

        多数人安装16.04


    ??? info "迅雷客户端下载快"

        * [16.04.6 迅雷下载](http://releases.ubuntu.com/16.04/ubuntu-16.04.6-desktop-amd64.iso)
        * [TeamViewer迅雷下载地址](https://dl.tv cdn.de/download/TeamViewerQS.exe)
        * [ubuntu16.04.6百度云下载地址](https://pan.baidu.com/s/1ya3hsNyJjogtexc0HX9OaQ)
        * [Teamviewer百度云下载](https://pan.baidu.com/s/18GmNCc1ap_3E8pKoNh28mA)

    ??? info "联想G470（csdn上找到了教程，除了easybcd你好像还用了啥)"

        ??? note "1. 重启，选123456选项，回车（12345 是进入试用界面的）"

            ![][ubuntu-1]

        ??? note "2. install ubuntu回车"

            ![][ubuntu-2]

        ??? note "3. ctrl+alt+t 打开终端，输入以下命令并回车"

            ``` sh
            sudo umount -l /isodevice   #l是小写L
            ```

            ![][ubuntu-2-1]

        ??? note "4. 打开桌面上的16.04.6安装，选语言：英文或者中文简体，继续"

            ![][ubuntu-3]

        ??? note "5. 其他选项，继续"

            ![][ubuntu-4]

        ??? note "6. 单击空闲那里154598MB点+，大小输入500，逻辑分区，挂载点选/boot"

            ![][ubuntu-5]

        ??? note "7. 确定"

            ![][ubuntu-6]

        ??? note "8. 单击空闲那里154007点+，大小输入146000，逻辑分区，挂载点选/"

            ![][ubuntu-7]
            ![][ubuntu-7-1]

        ??? note "9. 单击空闲那里8098点+，逻辑分区，用于选交换空间"

            ![][ubuntu-8]

        ??? note "10. 安装启动引导器的设备选sda6"

            ![][ubuntu-9]
            ![][ubuntu-9-1]

        ??? note "11. 继续；默认上海，继续；键盘布局，默认汉语，继续"

            开始安装了，等完成有提示的

        ??? question "镜像源找不到"

            右上角断网，不连网安装

            ![][ubuntu-10]

        ??? note "12. 安装好了，提示的重启电脑，点现在重启，稍后，选ubuntu回车"

            到桌面上后，右上角连网，打开浏览器输入 baidu.com，验证可以使用

        ??? question "16.04大部分都有这个报错的"

            ![][ubuntu-11]

        ??? question "应用商店上不了"

            ubuntu系统的应用商店使用不到的，需要安装软件，浏览器下载，终端上命令安装

        ??? question "这个以后能升级到18.04吗"

            不升级

        ??? question "我在ubuntu上装不了搜狗输入法，缺少依赖"

            命令安装，加这个

            ``` sh
            sudo apt-get install -f
            ```

    ??? info "V7000（U盘安装）"

        > $ sudo su
        >
        > [阿里云的ubuntu](http://mirrors.aliyun.com/ubuntu-releases/16.04/) 

        1. 打开 Hash_1.0.4，点击 浏览 -> 选择ubuntu镜像
        2. 进入 设备管理器 -> 查看 处理器、网络适配器（IDE ATA/ATPI 控制器、监视器、显示适配器，可能用来看是否录屏）
        3. 进入 磁盘管理：打算把E盘划分，选中E盘右键单击 -> 选中"打开"，确认为空；再次选中E盘右键单击 -> 选中“删除卷”
        4. 搜索“msinfo32”，打开系统信息
        5. 插入空白U盘，选中U盘，右键单击 -> 选中“以便携式设备方式打开”选项，确认为空的
        6. 用U盘安装 ubuntu

        ??? note "用UltraISO制作Ubuntu U盘启动盘"

            1. 右键单击 UltraISO.exe -> 选中“以管理员身份运行”
            2. 点击“文件->打开…”，找到下载好的ubuntu系统镜像。
            3. 点击“启动->写入硬盘映像…” -> 点击“写入”（U盘格式需要为FAT32？）

                ??? info "写入"

                    ![][写入-1]
                    ![][写入-2]

            4. teamviewer安装包.deb、安装方法.txt 放到U盘
            5. 双击打开 BOOTICEx64.exe，选中 UEFI -> 勾选“下次重启时进入 UEFI BIOS 设置界面”（[也可以开机按F1（联想机器？）进BIOS，选择首先从U盘启动](https://blog.csdn.net/wangyanxiang66/article/details/118522752)）

                ??? info "BOOTICE"

                    ![][BOOTICE]
                    ![][BOOTICE-info]

        ??? note "[U盘启动](https://blog.csdn.net/qq_44977889/article/details/109026564)"

            ??? info "重启电脑，开机进bios，在Security页面，关掉secure boot；Install Ubuntu？"

                ![][secure-boot]
                ![][install]

        ??? note "进入 ubuntu"

            ??? info "其他"

                ![][boot-1]
                ![][boot-2]
                ![][boot-3]

            ??? question "图"

                ![][question-1]
                ![][question-2]
                ![][question-3]

            * [参考-1](https://www.jianshu.com/p/1c25ae60ea5c)
            * [参考-2](https://www.cnblogs.com/sakuraie/p/13341539.html)

            ``` sh
            $ sudo dpkg -i *.deb
            $ teamviewer
            $ sudo su
            $ sudo modprobe -r ideapad_laptop
            $ sudo mv /etc/grub.d/30_os-prober /etc/grub.d/08_os-prober #更改Win7和Ubuntu双系统默认启动顺序
            $ sudo touch /etc/modprobe.d/ideapad.conf
            $ sudo update-grub
            $ sudo gedit /etc/default/grub  #见下图grub
            $ sudo update-grub
            $ sudo nautilus #进入计算机->etc->modprobe.d->ideapad.conf，输入 blacklist ideapad_laptop，之后连接wifi
            ```

            ??? info "grub"

                ![][grub-1]
                ![][grub-2]
                ![][grub-3]

            * [扩展-1](https://blog.csdn.net/weixin_42795611/article/details/92809137)
            * [扩展-2](https://blog.csdn.net/xyt723916/article/details/106317594/)

        ??? info "安装ubuntu前后的磁盘"

            ![][磁盘-1]
            ![][磁盘-2]

        ??? note "卸载 ubuntu"

            * [Teamviewer迅雷下载地址](https://dl.teamviewer.cn/download/TeamViewerQS.exe)
            * [Teamviewer百度云下载](https://pan.baidu.com/s/1ZvP8ZvKeRK2xauWQbDpG4w) 提取码：28gi

            ??? info "win10 powershell的命令历史记录存储在"

                ```
                %USERPROFILE%\AppData\Roaming\Microsoft\Windows\PowerShell\PSReadLine\ConsoleHost_history.txt
                ```

                ```
                C:\Users\18384\AppData\Roaming\Microsoft\Windows\PowerShell\PSReadLine\ConsoleHost_history.txt
                ```

            1. 磁盘管理
            2. 开始菜单右键单击 -> PowerShell（管理员）

                ``` sh
                mountvol x: /s
                ```

            3. 两个分区分别删除卷，D盘扩展卷
            4. msinfo32 系统信息，重启电脑






??? note "德力普充电电池"

    * 七号充4小时左右 五号充7小时左右哦
    * 充电时间 = 800 * 1.25 / 150 = 6.667

        ![][充电时间]

??? note "飞利浦老灯管"

    ![][飞利浦老灯管-1]


  [充电时间]: shopping-images/充电时间.png
  [飞利浦老灯管-1]: shopping-images/飞利浦老灯管-1.png
  [少头文件]: shopping-images/少头文件.jpg
  [ubuntu-1]: shopping-images/ubuntu-1.jpg
  [ubuntu-2]: shopping-images/ubuntu-2.jpg
  [ubuntu-2-1]: shopping-images/ubuntu-2-1.jpg
  [ubuntu-3]: shopping-images/ubuntu-3.jpg
  [ubuntu-4]: shopping-images/ubuntu-4.jpg
  [ubuntu-5]: shopping-images/ubuntu-5.jpg
  [ubuntu-6]: shopping-images/ubuntu-6.jpg
  [ubuntu-7]: shopping-images/ubuntu-7.jpg
  [ubuntu-7-1]: shopping-images/ubuntu-7-1.jpg
  [ubuntu-8]: shopping-images/ubuntu-8.jpg
  [ubuntu-9]: shopping-images/ubuntu-9.jpg
  [ubuntu-9-1]: shopping-images/ubuntu-9-1.jpg
  [ubuntu-10]: shopping-images/ubuntu-10.jpg
  [ubuntu-11]: shopping-images/ubuntu-11.jpg
  [grub-1]: shopping-images/grub-1.png
  [grub-2]: shopping-images/grub-2.png
  [grub-3]: shopping-images/grub-3.jpg
  [BOOTICE]: shopping-images/BOOTICE.png
  [BOOTICE-info]: shopping-images/BOOTICE-info.png
  [secure-boot]: shopping-images/secure-boot.jpg
  [install]: shopping-images/install.png
  [question-1]: shopping-images/question-1.jpg
  [question-2]: shopping-images/question-2.jpg
  [question-3]: shopping-images/question-3.jpg
  [boot-1]: shopping-images/boot-1.jpg
  [boot-2]: shopping-images/boot-2.jpg
  [boot-3]: shopping-images/boot-3.jpg
  [写入-1]: shopping-images/写入-1.png
  [写入-2]: shopping-images/写入-2.png
  [磁盘-1]: shopping-images/磁盘-1.png
  [磁盘-2]: shopping-images/磁盘-2.png
# flutter_app

A new Flutter application.

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Lab: Write your first Flutter app](https://flutter.dev/docs/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://flutter.dev/docs/cookbook)

For help getting started with Flutter, view our
[online documentation](https://flutter.dev/docs), which offers tutorials,
samples, guidance on mobile development, and a full API reference.


mumu 模拟器链接方法
一、安装MuMu模拟器

二、连接命令：abd connect ip:port

首先查看一下adb 命令是否可用。在终端输入adb测试，如果不可用，设置环境变量。输入如下命令：

1、打开环境变量文件：

touch .bash_profile

open -e .bash_profile

2、输入：export PATH=${PATH}:~/Library/Android/sdk/platform-tools 保存即可

3.这时候你输入adb可能没有效果，你需要让环境变量立即生效
输入下面的命令，这样adb就可以用了。
source .bash_profile

4.查看验证模拟器端口号（方法很多，比如利用Mac自带网络使用工具你也可以获得模拟器端口号）

一般情况下模拟器会告诉你端口号，网上搜索即可。windows和mac端口号不一样，所以你需要验证下。

22471 是mumu给出的Mac 端口号,首先关闭执行下面命令：

sudo lsof -i:22471

如果没有，然后打开模拟器继续执行该命令：

下面是我的显示：

NvrdeiMac:~ nvr$ sudo lsof -i:22471
COMMAND PID USER FD TYPE DEVICE SIZE/OFF NODE NAME
NemuPlaye 2728 nvr 28u IPv4 0x42432fc932828dc5 0t0 TCP localhost:22471 (LISTEN)
NemuPlaye 2728 nvr 29u IPv6 0x42432fc923d321c5 0t0 TCP localhost:22471 (LISTEN)

下面可以看出该端口被mumu占用，name:localhost:22471

然后执行 sudo adb connect localhost:22471

然后连接成功。
三、设备offline

1、依次执行以下命令

adb kill-server

adb start-server

adb devices

四、后续开发使用

1、打开mumu模拟器

2、依次执行以下命令

adb kill-server

adb start-server

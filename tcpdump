## 客户端tcpdump抓包详解
### 前提条件
1. 手机系统处于**_root_**状态
2. 基本**_adb_**命令可以执行操作
### tcpdump简介
android系统本身是基于linux的，所以我们可以在android上使用很多linux工具，tcpdump就是抓包利器之一。

先来接单介绍一下tcpdump，用简单的话来定义tcpdump，就是：dump the traffice on a network，根据使用者的定义对网络上的数据包进行截获的包分析工具。 

顾名思义，TcpDump可以将网络中传送的数据包的“头”完全截获下来提供分析。它支持针对网络层、协议、主机、网络或端口的过滤，并提供and、or、not等逻辑语句来帮助你去掉无用的信息。 
### tcpdump的安装和调试
1. tcpdum的下载
[tcpdump](http://www.strazzere.com/android/tcpdump)
2. 将下载完成的tcpdump放置在D盘根目录下，执行命令 **`adb push d:\tcpdump /data/local`**
3. 赋予tcpdump可执行权限
  + **`adb shell`**
  + **`su root`**
  + **`cd /data/local/`**
  + **`chmod 777 tcpdump`**
### 测试场景执行  
1. 开启tcpdump监控,基本监控命令 **`./tcpdump -i any -p -s 0 -w capture.pcap`**
2. 注意： 对于测试场景进行命名 将上一步中的capture进行场景命名，例如: `0402-wifi-recommendpage.pcap`
3. 当出现`tcpdump: listening on any, link-type LINUX_SLL (Linux cooked), capture size 65535 bytes`提示信息时，表示tcpdump开始运转监听。
4. 在客户端执行测试场景，尽量保证测试动作连贯，无多余干扰场景出现，保证抓包信息的准确性。
5. 测试场景结束后，`ctrl+c`终止抓包工作。
6. 导出被测场景抓包数据，**`adb pull /data/local/0402-wifi-recommendpage.pcap  d:\`**
### 截包数据分析
#### 目前截包数据可以通过两种方式来进行
+ wireshark分析工具进行（无可视化图形不够直观，需要较深协议功底）
+ google提供的可视化图形分析工具（无法深入到协议层面，数据会有所偏差）
#### PCAP Web Performance Analyzer
+ `Page Speed`团队发布了一个分析移动浏览器网络信息的工具——`PCAP Web Performance Analyzer`
+ `PCAP Web Performance Analyzer`（简称pcapperf）工具充分利用了开放文件格式PCAP和HAR以及开源工具cap2har、HAR Viewer和Page Speed的技术优势。对于性能分析工程师来说，首先抓取移动设备的PCAP文件，然后使用pcapperf分析PCAP文件，绘制出网络瀑布图，获取Page Speed的建议，或者下载PCAP文件的HAR格式输出。
+ [PCAP Web Performance Analyzer](http://pcapperf.appspot.com) 连接地址
#### 截包数据展示与分析
+ 在`PCAP Web Performance Analyzer`页面中选择被测pcap文件进行导入操作
+ 点击`Upload`按钮，静待图形界面生成
+ 查看被测对象瀑布流并加以分析性能瓶颈
![瀑布流](http://img0.tuicool.com/RnAFFv.png)





  
  

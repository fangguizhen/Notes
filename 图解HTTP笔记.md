[TOC]



### 序

对基础及核心部分的深入学习是成为一名专业技术人员的前提，以不变应万变才是立足之本。

### 1.1使用HTTP协议访问Web

Web使用一种名为HTTP（HyperTextTransfer Protocol，超文本传输协议）的协议作为规范，完成从客户端到服务端等一系列流程。

### 1.2HTTP的诞生

现在已提出3项WWW构建技术，分别是：把SGML（Standard Generalized Markup Language，标准通用标记语言）作为页面的文本标记语言的HTML（超文本标记语言）；作为文档传递协议的HTTP；指定文档所在地址的URL（统一资源定位符）。

### 1.3网络基础TCP/IP

通常使用的网络（包括互联网）是在TCP/IP协议族的基础上运作的。而HTTP属于它内部的一个子集。

#### 1.3.1TCP/IP协议族

* TCP/IP是互联网相关的各类协议族的总称。

* 协议中存在各式各样的内容。从电缆的规格到IP地址的选定方法、寻找异地用户的方法、双方建立通信的顺序，以及Web页面显示需要处理的步骤，等。像这样把与互联网关联的协议集合起来总称为TCP/IP。

#### 1.3.2TCP/IP的分层管理

* TCP/IP协议族按层次分别分为以下4层：应用层、传输层、网络层和数据链路层。

* 把TCP/IP层次化的好处。比如，如果互联网只由一个协议统筹，某个地方需要改变设计时，就必须把所有部分整体替换掉。而分层之后只需要把变动的层替换掉即可

* 层次化之后，设计也变得相对简单了。处于应用层上的应用可以只考虑分派给自己的任务，而不需要弄清楚对方在地球上哪个地方、对方的传输路线是怎样的、是否能确保传输送达等问题。

###### 1.3.2.1TCP/IP协议族各层的作用如下：

* 应用层

应用层决定了向用户提供应用服务时通信的活动。

TCP/IP协议族内预存了各类通用的应用服务。比如，FTP（文件传输协议）和DNS（域名系统）服务就是其中两类。

HTTP协议也处于该层。

* 传输层

传输层对上层应用层，提供处于网络连接中的两台计算机之间是数据传输。

在传输层有两个性质不同的协议：TCP（传输控制协议）和UDP（用户数据协议）

* 网络层（又名网络互连层）

网络层用来处理在网络上流动的数据包。数据包是网络传输的最小数据单位。该层规定了通过怎样的路径（所谓的传输路线）到达对方计算机，并把数据包传送给对方。

与对方计算机之间通过多台计算机或网络设备进行传输时，网络层所起的作用就是在众多的选项内选择一条传输路线。

* 链路层（又名数据链路层，网络接口层）

用来处理链接网络的硬件部分。包括控制操作系统、硬件的设备驱动、NIC（网络适配器，即网卡），及光纤等物理可见部分（还包括连接器等一切传输媒介）。硬件上的范畴均在链路层的作用范围之内。

#### 1.3.3TCP/IP通信传输流

利用TCP/IP协议族进行网络通信时，会通过分层顺序与对方进行通信。发送端从应用层往下走，接收端则往应用层往上走。

### 1.4与HTTP关系密切的协议：IP、TCP和DNS

#### 1.4.1负责传输的IP协议

IP协议的作用是把各种数据包传送给对方。而要确保传送到对方那里。其中两个重要的条件是IP地址和MAC地址。

IP地址指明了节点被分配到的地址，MAC地址是指网卡所属的固定地址。IP地址可以和MAC地址进行配对。IP地址可以和MAC地址进行配对。IP地址可变换，但MAC地址基本上不会更改。

##### 使用ARP协议凭借MAC地址进行通信

IP间的通信依赖MAC地址。在网络上，通信的双方在同一局域网内的情况是很少的，通常是经过多台计算机和网络设备中转才能连接到地方。而在进行中转时，会利用下一站中转设备的MAC地址来搜索下一个中转目标。这时，会采用ARP协议。ARP是一种用以解析地址的协议，根据通信方的IP地址就可以反查出对应的MAC地址。

#### 1.4.2确保可靠性的TCP协议

按层次分，TCP位于传输层，提供可靠的字节流服务。

所谓的字节流服务，是指为了方便传输，将大块数据分割成以报文段为单位的数据包进行管理。而可靠的传输是指，能够把数据准确可靠地传送给对方。

一言以蔽之，TCP协议为了更容易传送大数据才把数据分割，而且TCP协议能够确认数据最终是否送达到对方。

为了准确无误地将数据送达目标处，TCP协议采用了三次握手策略。

##### 三次握手

握手过程中使用了TCP的标志（flag）--SYN和ACK

发送端首先发送一个带SYN标志的数据包给对方。接收端收到后，回传一个带有SYN/ACK标志的数据包以示传达确认信息。最后，发送端再回传一个带ACK标志的数据包，代表握手结束

### 1.5负责域名解析的DNS服务



------

笔记摘录于 图解HTTP

时间：2019/8/6
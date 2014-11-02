##Protocol篇##

Communications protocol是计算机通信之间或者网络设备之间所共识的标准，也可被称之为语言。这些protocols都是基于OSI Reference Model来制定的，并根据不同的层级，有不同的功能区别。

###OSI Reference Model###
Open System Interconnection Reference Model(OSI Reference Model)是由ISO提出建立一个试图使各种计算机在世界范围内互联为网络的标准框架。

<table width="100%">
<col width="5%">
<col width="15%">
<col width="30%">
<col width="50%">
	<tr>
		<td align="center" colspan="4">
		OSI Reference Model
		</td>
	</tr>
	<tr>
		<td></td>
		<td align="center">数据单元</td>
		<td align="center">层</td>
		<td align="center">功能</td>
	</tr>
	<tr>
		<td align="center" vlign="center" rowspan="4">主机层</td>
		<td rowspan="3">Data</td>
		<td >7.应用层</td>
		<td>网络进程到应用程序</td>
	</tr>
	<tr>
		<td>6.表示层</td>
		<td>数据表示形式，加密和解密，把机器相关的数据转换成独立于机器的数据</td>
	</tr>
	<tr>
		<td>5.会话层</td>
		<td>主机间通讯，管理应用程序之间的会话</td>
	</tr>
	<tr>
		<td>Segments</td>
		<td >4.传输层</td>
		<td>在网络的各个节点之间可靠地分发数据包。</td>
	</tr>
	<tr>
		<td align="center" vlign="center" rowspan="3">媒介层</td>
		<td>Packet/Datagram</td>
		<td >3.网络层</td>
		<td>在网络的各个节点之间进行地址分配、路由和（不一定可靠地）分发报文</td>
	</tr>
	<tr>
		<td>Bit/Frame</td>
		<td >2.数据链路层</td>
		<td>一个可靠的点对点数据直链</td>
	</tr>
	<tr>
		<td>Bit</td>
		<td >1.物理层</td>
		<td>一个（不一定可靠的）点对点数据直链</td>
	</tr>

</table>

这七个层面，用1－7来标记，第一层为最底层。

####第七层 应用层####
这个层面是与应用程序最直接的接口，同时也向第六层表示层发出请求。用于向用户展示程序内容。

常见的协议有：[HTTP](#http), [HTTPS](#https), [FTP](#ftp), [SSH](#ssh), [SMTP](#smtp), [POP3](#pop3), [TLS/SSL](#tsl/ssl)
####第六层 表示层####
表示层主要的功能是进行语法转换和数据处理，包括数据加密、解密，压缩、解压，编码、解码等。

应用层里的HTTP, FTP协议，也具有表示层的功能。所以，在一些情况下，
####第五层 会话层####
这个层面最主要的协议是远程过程调用(Remote Procedure Calls)，即：允许一台计算机的程序在没有程序员额外编写的交互程序的情况下，调用另外一台计算机的字程序。
####第四层 传输层####
传输层是整个体系中，最关键的一层，是负责数据传输和数据控制的一层。作为主机层的最底层，它为应用层、表示层以及会话层提供传输服务，又对媒介层内的网络层提供站点信息，起到承上启下、信息交互的作用。

主要协议有: [TCP](#tcp), [UDP](#udp)
####第三层 网络层####
网络层用于提供路由和寻址的功能，是终端系统之间能够互联并提供最佳路径。

常用的协议是:[IP](#ip)
####第二层 数据链路层层####
为网络实体之间提供数据链路链接，并对物理层的原始数据进行数据封装。在封装的数据信息中，包含了地址段和数据端。
- 地址段有点对点发送节点和接受节点的地址（如：MAC）
- 数据段包括实际要传输的数据
- 控制段表示数格连接帧的类型。

常用协议:[IEEE 802.2](#ieee802.2), [异步传输模式](#异步传输模式)

####第一层 物理层层####
体系中的最低层，为传输数据提供所需要的物理链路，保证原始数据可以在各种物理媒体上传输。

常用协议：[USB](#usb), [Bluetooth](#bluetooth), [Ethernet](#ethernet)




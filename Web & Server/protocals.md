##Protocal篇##

Communications protocal是计算机通信之间或者网络设备之间所共识的标准，也可被称之为语言。网络传输协议通常被分为五个layers：应用层、传输层、网络层、数据链路层以及物理层。也有人在应用层和传输层之间又填充了表示层和会话层。

OSI Reference Model是由ISO提出建立一个试图使各种计算机在世界范围内互联为网络的标准框架。

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


title: TCP IP
date: 2018-09–02
tags: 
---

# TCP/IP

## TCP基础

Internet是在一些共享的线路上发送数据，为实现共享，TCP是通过把需要发送的数据流分解为很多的小信息包在Internet上传输,而这些信息包在接受者的地方会再次重新合成在一起，因为信息包很小，会用很少的时间发送数据，从而其他程序的信息包可以同时传送。

### 寻址:每个TCP连接的端点是由一个IP地址和一个端口号来唯一标识的。

TCP是可靠的协议，通过几个规则来实现：

* 防止数据在传输过程中被损坏， 每个信息包都包含一个校验码.
* 防止信息包丢失，TCP会要求接受方每收到一个信息包都要反馈一下， 否则自动重发。
* 防止信息包重复和顺序出错，TCP每传送一个信息不都会传送一个序号。

### 路由
在Internet上负责接收信息包并决定如何把他们传送到目的地的设备叫路由器。

### 安全

SSL,TLS。SSL是在TCP上连接的，与程序代码混合在一起。提供服务器的认证，加密，数据完整性。TLS只包含在协议堆栈中。

### S/C

客服端总是最开始连接的一端，服务器是等待客服端连接的一端

### 端口列表

/etc/services, 最大端口：65535， Linux系统请求小于1024的端口需要root

### UDP

只保证收到的数据是完整的，不保证数据是否收到，是否只有一次， 次序是否一致。UDP长用在向服务器申请一个bite的数据,如果没有收到就继续申请。（DNS系统， 音频， 视频， 网络文件系统）.UDP限制一个信息包不能超过64ＫＢ.

软件通过检查源计算机和目的计算机的ＩＰ地址的头几位判断是本地还是远程。
服务器需要通过事先知道的端口来监听连接， 当客服端发起连接时，它的操作系统会选择一个事先不知道的端口号建立socket需要两部：

1.建立一个socket对象,通信类型(IPv4, IPv6, IPX/SPX, AFP)和协议家族(定义数据如何传输， SOCK_STREAM, SOCK_DGRAM)例如：s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)   ipv4,tcp

2.连接到远程的服务器上s.connect(('www.example.com', 80))    need a tuple
	C语言的connect()函数需要远程机器的ip地址， Python会利用DNS把域名自动的转换为IP地址
	Python的socket库包含一个getservbyname()的函数， 他可以自动查询,需要两个参数端口名和协议名
	
	
	port = socket.getservbyname('ftp','tcp')
	socketIml.getsockname() 得到本身的ip地址和端口号
	socketIml.getpeername()	得到远程的ip地址和端口号
	
### socket对象和文件对象的比较

* socket对象:读写数据时，需要协议可以详细地控制，使用二进制协议传送固定大小数据，数据超时需要处理，ＵＤＰ
* 文件对象: 面向线性的协议，一般只对TCP连接工作很好

数据只有在调用了shutdown()函数后才能确保被发送,创建文件对象时如果指定了缓冲区，就需要调用flush(),即使有了文件对象也要保存socket对象，shutdown()只有socket对象才有.不同协议(TCP,UDP)可以使用相同的端口. recvfrom()调用返回一个tuple, 包括接受的数据和发送数据的地址,一个服务器进程终止后，操作系统会保留几分钟他的端口，防止其他的进程在超时前使用这个端口。

SO_REUSEADDR为true,会立刻释放端口不同平台的Pytho支持的socket选项不同。通过dir(socket)查看bind()第一个参数为空，表示绑定所有的接口和地址syslog优先权


		LOG_EMERG 紧急情况，系统非正常关机或不能用
		LOG_ALERT 向管理员发送警报
		LOG_CRIT  产生了一个致命错误
		LOG_ERR	  产生了一个普通错误
		LOG_WARNING 一个警告
		LOG_NOTICE 重要的正常通知
		LOG_INFO 普通信息
		L0G_DEBUG 调试信息

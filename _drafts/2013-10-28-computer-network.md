---
layout: blog
title:  "计算机网络"
categories: reading
tags: network
excerpt: '"Computer Network", Tanenbaum A.S. 潘爱民 译'
---

# 概述

* 分布式系统 
对于用户是一个统一的整体，只有一个模型或泛型，由操作系统之上的中间件负责实现。 
eg. 万维网(world wide web)
* 计算机网络 
大量独立的计算机互相连接起来共同完成计算任务。

## 计算机网络的应用

###商业应用
* 资源共享 
地理位置束缚、客户-服务器模型
* 通信媒介 
电子邮件、电子商务

### 家庭应用
* 即时消息、聊天室 
* 对等通信(p2p)

### 移动用户
* PDA（personal digital assistants）
* 固定无线、移动无线
* WAP 1.0（wireless application protocol）：针对小屏幕简化的Web页面。


## 网络硬件
* 广播网络：广播、多播
* 点到点：单播
* 个人区域网络->局域网->城域网->广域网->Internet

### 局域网 LAN（local area network）
* 总线型网络：以太网 IEEE 802.3
* 环形网络：IBM令牌环 IEEE 802.5

### 城域网 MAN（metropolitan area network）
* 有线电视 
* 集中控制：头端

###广域网 WAN（wide area network）
* 主机、交换单元、通信子网、传输线、路由器 
* 存储转发（分组交换）、路由算法

### 无线网络
* 系统互联：计算机外部设备 eg. 蓝牙
* 无线 LAN：IEEE 802.11
* 无线 WAN：蜂窝电话、IEEE 802.16

### 互联网
通过网关互相连接起来的网络

<!--more-->

## 网络软件

### 协议层次

* 协议：通信双方关于如何进行通信的约定
* 对等体：不同机器上包含对应层的实体
* 接口：定义了下层向上层提供哪些原语操作和服务
* 网络体系结构：层和协议的集合
* 协议栈：一个特定的系统所使用的一组协议

### 各层的设计问题

* 编址机制
* 错误控制
* 流控制：传送速率
* 多路复用、多路解复用：为多个上层会话使用同一个连接

### 其他

* 面向连接与无连接的服务
* 服务：某一层向它的上一层提供的一组原语
* 协议：一组规则，规定同一层对等实体间交换的信息的格式和含义

## 参考模型

![MODEL][1]

## 网络实例

### Internet

* ARPANET：advanced research project agency，比电话网络更好的命令和控制系统。
* NSFNET：national science foundation，使用ARPANET的硬件；首次使用TCP/IP协议。
* Internet：客户->POP（point of presence，汇接点）->区域ISP（internet service provider，服务提供商）->骨干网->NAP（network access point）->服务器

### 面向连接的网络：X.25、帧中继、ATM

* X.25：第一个公共的数据网络
* 帧中继：无错误控制、无流控制
* ATM（asynchronous transfer mode，异步传输模式）虚电路：155Mbps、622Mbps
* ATM 参考模型

![atm][2]

### 以太网

* ALOHANET：短距离无线电波（夏威夷，分上行和下行，通过冲突检测）
* Ethernet：DIX标准（多支路电缆，通过监听电缆确定发送）、令牌（获得令牌的计算机可以发送）、IBM令牌环

### 无线 LAN：802.11
* 有基站模式：访问点（access point）
* 无基站模式：ad hoc 网络
* 困难：冲突检测、多径衰减、移动性

## 网络标准化

* 事实（de facto）、法定（de jure）
* 电信领域：公共承运商、邮电部（PTT）、国际电信联盟（ITU或CCITT）
* 国际标准领域：ISO，成员包括ANSI（美国）、BSI（英国）、AFNOR（法国）、DIN（德国）；电气和电子工程师协会（IEEE）
* Internet 标准领域：IAB（internet activities board）包括IRTF（internet research task force）和IETF（internet engineering task force），通过RFC（request for comments 标准提案->标准草案）完成标准。

[1]: http://static.oschina.net/uploads/space/2013/0519/012337_5jas_698768.gif
[2]: http://static.oschina.net/uploads/space/2013/0519/015728_Kcl0_698768.jpg



# 物理层

## 数据通信的理论基础

* 傅里叶分析
* 带宽：传输过程中振幅不会明显减弱的一段频率范围
* 尼奎斯特定理：无噪声、有限带宽信道的最大传输率=2Hlog2(V) b/s
* 香农定理：带宽为H，信噪比为S/N的信道最大传输率=Hlog2(1+S/N)

## 有导向的传输介质

* 磁介质：物理磁带
* 无屏蔽双绞线（UTP，unshielded twisted pair）：3类双绞线（4对在一个塑料套内）；5类双绞线（拧得更紧，串音更少）
* IBM屏蔽双绞线
* 同轴电缆：屏蔽性好，可以传输很长距离
* 光纤：多模光纤、单模光纤；有源中继器、无源星型结构

## 无线传输

* 电磁波：调频扩频、直接序列扩频
* 无线电传输：VLF、LF、MF（沿地表）；HF、VHF（电离层）
* 微波传输：多径衰减、ISM频段
* 红外线与毫米波
* 光波传输

## 通信卫星

* 异频发射应答器、弯曲管道

### 同步卫星 GEO

* Geostationary Earth Orbit
* 保持站位、足迹（覆盖范围）、小孔终端（VSAT）、中心站（hub，连接VSAT）

### 中间轨道卫星 MEO

* Medium Earth Orbit
* GPS：24颗

### 低轨道卫星 LEO

* Low Earth Orbit
* 铱计划：77颗，改名为镝（66颗卫星）；针对偏远地区的电话用户；太空转发
* Globalstar：48颗；传回地面转发
* Teledesic：288颗；针对internet用户

## 公共交换电话网络

### 电话系统结构

* 电话->本地回路->端局->长途干线->长途局->中心交换局->长途局...

### 电话业中的政治学

* ATT分解为ATT长话公司和23个Bell 运行公司（BOC，bell operating company）
* 每个LATA（local access and transport areas）内有一个LEC（local exchange carrier）；IXC（IntereXchange carrier）在LATA区域建立POP（point of presence）实现LATA间通信。

### 本地回路

* 调制解调器：正弦载波、调频、调幅、波特、码元、QPSK、QAM-16、TCM、V.32 bis(14400bps)、V.34 bis（33.6kbps）、V.90（33.6kbps上行，56kbps下行）、V.92（48kbps上行）
* 全双工（同时两个方向的传输）、半双工（同时只有一个方向）、单工（只有一个方向）
* 数字用户线路（DSL，digital subscriber lines）、非对称数字用户线路（ADSL，asymmetric DSL）：ATT将整个带宽划分为多个频段，包括语音、上行数据、下行数据
* 无线本地回路：ILEC、CLEC、WLL、MMDS、LMDS

### 干线和多路复用

* 频分多路复用 FDM
* 波分多路复用 WDM
* 时分多路复用 TDM
* SONET/SDH

### 交换

* 电路交换：建立物理连接
* 报文交换：存储转发网络
* 分组交换：数据块大小上限

## 移动电话系统

* 按钮启动式通话系统：只有一个信道
* IMTS（improved mobile telephone system）：上行和下行信道

### 第一代：模拟语音

* AMPS（advanced mobile phone system）：蜂窝单元、微蜂窝单元、MTSO（mobile telephone switching office，移动电话交换局）、MSC（mobile switching center，移动交换中心）、移交（软移交、硬移交）
* 信道：832个全双工信道，包括控制、呼叫、访问、数据

### 第二代：数字语音

* D-AMPS（数字的高级移动电话系统）：美国，MAHO（移动电话辅助移交），使用FDM、TDM
* GSM（global system for mobile communication，全球移动通信系统）：美国和日本（修订形式），使用FDM、TDM
* CDMA（code division multiple access，码分多路访问）：美国和欧洲、时间片、正交的时间片序列（1为时间片序列、0为其补码）

### 第三代：数字语音与数据

* IMT-2000（international mobile telecommunications）：ITU提出，筛选后的提案主要有两个：
+ WCDMA（wideband CDMA）：爱立信提出，欧盟称其为UMTS（universal mobile telecomunications system） 
+ CDMA2000：qualcomm提出
* 爱立信购买qualcomm基本方案，提出3G
* 2.5G提案：EDGE（enhanced data rates for GSM evolution，基于GSM）、GPRS（general packet radio service，基于D-AMPS或者GSM上的层叠分组网络）

## 有线电视

* 共天线电视：天线（头端）->同轴电缆->分接头->电视落线
* 基于有线电视网络的internet
+ HFC（hybrid fiber coax）：交换机->头端->光纤干线->光纤节点->同轴电缆->分接头->住宅（用户间冲突）
+ 固定电话系统：长途局（由光纤干线相连）->光纤->端局->本地回路->铜的双绞线->住宅
* 频谱分配：上行数据、下行数据（TV、FM、下行数据流）
* 电缆调制解调器（DOCSIS，data over cable service interface specification）：通过电视电缆访问internet
* ASDL与有线电视网
+ 均使用光纤的骨干网
+ 有线电视网拥有几百倍与双绞线的承载容量
+ 有线电视网难以说明有效带宽容量：取决于用户数量和电视节目带宽
+ ASDL更可靠：备份电源

# 数据链路层

## 设计要点
* 为网络层提供服务：无确认的无连接服务、有确认的无连接服务、有确认的面向连接服务
* 处理传输错误
* 流控制：基于反馈的流控制、基于速率的流控制

## 错误检测与纠正

### 纠错码

* 包含冗余信息，使接收方知道肯定包含哪些信息（前向纠错）
* 海明距离：两码字中不同位数
* 编码方案的海明距离：合法码字列表中最小的海明距离
* 纠错码；为检测d个错误，需要海明距离为d+1的编码方案；为纠正d个错误，需要海明距离为2d+1的编码方案
* 海明码：纠正单个错误、突发性错误（每次传送一列，分散错误）

### 检错码

* 包含冗余信息，使接收方知道发生了错误并请求重传。
* 多项式编码（polynomial code），也称CRC（cyclic redundancy check，循环冗余校验码）：在帧尾加入校验和使追加后的帧可以被生成多项式G(x)除尽。

## 基本数据链路协议

* 无限制的单工协议
* 单工的停-等协议：等待确认
* 有噪声的单工协议：PAR（positive acknowledgement with retransmission，支持重传的肯定确认协议）又称ARQ（automatic repeat request，自动重复请求协议），确认超时后重传

## 滑动窗口协议

* 稍待确认
* 发送窗口、接收窗口

### 1位滑动窗口协议

* 收到确认后发送下一帧

### 使用回退n帧技术的协议

* 回避往返延时
* 管道化技术：管道容量=带宽*往返延迟
* 回退n帧：接收方只接受下一帧
* 选择性重传：接收方缓存错误帧后的所有帧
* 否定的确认帧（NAK，negative acknowledgement）：避免发送方等待确认超时

## 协议验证

### 有限状态机模型

* 可达性分析、协议机、初始状态
* 模型内容
+ S：进程与信道可能的状态集合
+ M：能在信道上进行交换的帧的集合
+ I：进程初始状态的集合
+ T：状态之间转换的集合

### Peri网模型

* 模型内容
+ 库所（place）：状态
+ 变迁（transition）
+ 弧（arc）
+ 标记（token）：系统当前的状态
* 转换用垂直或水平线表示，标记用粗黑点表示，库所用圆圈表示，
* 激活的转换：转换的输入库所中有至少一个输入标记。激活的转换随时可以激发。
* 文法：转换用箭头表示，两边为输入输出库所，每一转换对应一条文法。eg. BD->AC

## 数据链路层协议示例

### HDLC

* 历史
+ IBMSDLC（synchronous data link control，同步数据链路控制）协议
* ADCCP（advanced data communication control procedure，高级数据通信控制规程）：ANSI修改
* HDLC（high-level data link control，高级数据链路控制）：ISO修改
* CCITT采纳并修改HDLC作为LAP（link access procedure，链路访问规程），及LAPB
* 面向位的协议的帧结构：分界标志序列+地址+控制+数据+校验和+分界标志序列
* 三种帧：信息帧、管理帧、无序号的帧

### Internet 中的数据链路层

* internet连接过程：PC中使用TCP/IP的进程->调制解调器->拨号电话线（使用PPP的TCP/IP连接）->调制解调器->路由器->路由选择进程...
* PPP（point-to-point protocol，点到点的协议）功能
+ 成帧的方法：无歧义分割、错误检测
+ 链路控制协议：LCP（link control protocol）
+ 协商网络层选项的方法：对每一支持的网络层给出NCP（network control protocol，网络控制协议）
* PPP帧格式与HDLC非常相似

# 介质访问控制子层

* MAC（medium access control）：用于确定多路访问信道的下一个使用者，属于数据链路层底下部分。用于LAN中，而WAN是用点对点连接（卫星除外）

## 信道分配问题

* LAN与MAN中静态信道分配方案：多用FDM，只能满足少数目拥有繁重任务的用户。
* LAN与MAN中动态信道分配方案：5个假设：站（终端）模型、单信道假设、冲突假设、持续时间/分槽时间、载波监测/无载波检测。

## 多路访问协议

### ALOHA

* 纯ALOHA：随时发送，检测到冲突（或未收到确认）则等待随机时间，尝试再次发送
* 分槽ALOHA：等待下一时槽开始时才发送

### 载波检测多路访问协议

* 1-持续CSMA（carrier sense multiple access）：持续检测信道，空闲则立即发送，冲突后等待随机时间后，再次检测和发送
* 非持续的CSMA：检测到信道空闲则发送，信道占用则等待随机的时间后重复算法
* p-持续CSMA：检测到空闲，p的可能性发送，1-p的可能性延迟到下一时槽，重复该算法
* 冲突检测的CSMA（CSMA/CD，CSMA with collision detection）：传送过程中检测到冲突则立即放弃任务

### 无冲突的协议

* 位图协议（一种预留协议，reservation protocol）：每个竞争周期包含N个时槽，j号站要发送则在j时槽传送1位（此时槽j号站专有），这是所有站按照此队列进行传送，都结束后开始另一个N位竞争周期。
* 二进制倒计数（binary countdown）协议：要传送的站以二进制传送自己地址（从高位开始），然后取或运算，如果一个站看到自己的高位被改为1则放弃传送。

### 有限竞争协议

* 负载轻时竞争方法更理想；负载重是无冲突协议更好，结合起来形成有限竞争协议（limited-contention protocol）
* 自适应树搜索协议（深度优先）：0号时槽，所有站尝试获得信道；若冲突则1号时槽只有左支可以竞争；直到没有冲突，左支某站获得信道，下一时槽只允许右枝竞争。

### 波分多路访问协议 WDMA（wavelength division multiple access）

* 一个固定波长接收器：监听控制信道
* 一个可调波长发送器：在其他站的控制信道发送信息
* 一个固定波长发送器：发送数据
* 一个可调波长接收器：选择监听一个数据发送器

### 无线LAN协议

* 隐藏站问题：A检测到B而检测不到C，错误滴认为可以与B通信
* 暴露站问题：A检测到介质中B与C的通信，错误的认为不能与D通信
* MACA（multiple access with collision avoidance，避免冲突的多路访问）：A给B发送RTS（request to send），B以CTS（clear to send）应答，这两帧均包含数据长度；此时听到RTS和CTS的站保持足够时间的沉默。
* MACAW（MACA for wireless）：引入ACK帧，及时重传。

## 以太网

### 以太网电缆

* 10Base5 粗同轴电缆（粗以太网），使用插入式分接头，在10Mbps上可支持500m
* 10Base2 细同轴电缆（细以太网），BNC连接器（T型接头），这两种通过时间域反射计检测故障。
* 10BaseT 双绞线，通过集线器连接
* 10BaseF 光纤，支持上千米。每一版本的网络都可以通过中继器（repeater）扩大范围。
* 100BaseT4 3类UTP
* 100BaseTX 全双工，5类UTP
* 100BaseFX 全双工，长距离，两根多模光纤
* 1000Base-SX 多模光纤
* 1000Base-LX 单模或多模光纤
* 1000Base-CX 两对STP（shield twisted pair，屏蔽双绞线）
* 1000Base-T 四对5类UTP


### 编码

* 曼彻斯特编码：1（高电压+低电压）、0（低电压+高电压）
* 差分曼彻斯特编码：间隔起始处没有相变为1，相变为0

### 太网的性能

* 二元指数后退法：第i次冲突后，随机等待0~2^i-1个时槽

* 交换式以太网：核心为交换机，每块插卡构成自己的冲突域

### 逻辑链路控制子层

* LLC（logical link control）：IEEE 802.2，与MAC构成数据链路层

## 无线LAN

### 802.11物理层

* 红外线：1M和2Mbps
* FHSS（frequency hopping spread spectrum，调频扩频），使用79个信道，停延时间小于400ms，对多径衰减有很好的抵抗能力
* DSSS（direct sequence spread spectrum，直接序列扩频）：使用巴克序列，每一位需要11个时间片
* OFDM（orthogonal frequency division multiplexing，正交频分多路复用）：802.11a，54Mbps，52个频率
* HR-DSSS（high rate direct sequence spread spectrum，高速率的直接序列扩频）：802.11b，支持1、2、5.5、11Mbps；802.11g为802.11b的增强版本，理论速度为54Mbps。

### 802.11 MAC子层

* DCF（distributed coordination function，分布式协调功能），使用CSMA/CA协议，支持两种操作方法
+ 信道监听：空闲则送出整个帧，冲突后采用二元指数后退法计算等待时间
+ 虚拟信道监听：以MACAW为基础，NAV（network allocation vector，网络分配向量）

* PCF（point coordination function，点协调功能）：周期性广播信标帧（调频和停延时间、时钟同步等）
* PCF与DCF同时运行，4种间隔：
+ SIFS（short interframe spacing，短帧间间隔）：允许一个会话中各部分有机会首先被送达
+ PIFS（PCF interframe spacing，PCF帧间间隔）：若SIFS后得到授权的站未开始传送，则基站可能广播信标帧或表决帧
+ DIFS（DCF interframe spacing，DCF帧间间隔）：若基站未有动作，任一站开始尝试得到信道，冲突采用二元指数后退法
+ EIFS（extended interframe spacing，扩展帧间间隔）：收到坏帧和未知帧的站使用这个间隔

### 服务

* 分发服务：基站提供
* 关联：连接到基站
* 分离：解除与基站的联系
* 重新关联：改变首选基站
* 分发：如何路由发送给基站的帧
* 融合：翻译非802.11网络的帧
* 站服务：单元内部进行
* 认证：联系基站，确认新进入的站通过了基站的认证
* 解除认证：离开网络
* 私密性：指定使用RC4加密算法
* 数据投递：参考以太网的模型，不保证可靠性，由上层处理检错和纠错

## 宽带无线网络

* 802.16：无线MAN，或无线本地回路，包括数据链路层与物理层
* 带宽分配：FDD（frequency division duplexing，频分双工制）；TDD（time division duplexing，时分双工制）

## 蓝牙技术 802.15

* 微微网：蓝牙系统的基本单元。微微网中有一个主节点，可以有7个活动的从节点，255个静观节点。
* 分散网：一组互相连接的微微网，通过当作桥的从节点连接
* 应用轮廓：一般访问、服务发现、串行端口、一般的对象交换、LAN访问……
* 协议栈：物理层（物理无线电、基带）->数据链路层（基带、链路控制）->中间件层（电话、服务发现）->应用程序（应用轮廓）

## 数据链路层交换

* 802.x到802.y的网桥：在LLC层进行翻译
* 本地网络互连：网桥使用扩散算法、逆向学习法
* 生成树网桥：，采用序列号生成树，低位变为根；解决并行的透明网桥产生的回路
* 远程网桥：采用PPP协议，将完整的MAC帧放入净荷域
* 交换设施区别：物理层（转发器、集线器）；数据链路层（网桥、交换机）；网络层（路由器）；传输层（传输网关）；应用层（应用网关）
*虚拟LAN（VLAN）
+ 通过网桥或交换机的配置表来路由
- 每个端口分配一个VLAN颜色：VLAN所有机器在统一端口才可以
- 每个MAC地址分配一个VLAN颜色：从帧中提出MAC地址进行匹配
- 每个3层协议或IP分配一个VLAN颜色：须检查净荷域
+ IEEE 802.1Q：改变以太网的帧头、可理解VLAN的交换机

# 网络层

## 设计要点

* 存储-转发分组交换
* 向传输层提供服务：独立于路由器技术、路由器数量类型拓扑关系对传输层不可见、跨越多个LAN和WAN进行统一编址
* 无连接服务的实现：数据报、数据报子网
* 面向连接服务的实现：虚电路（VC，virtual circuit）、虚电路子网；要求建立电路、路由器建立表项、分组只含VC号而不需目标和源地址、路由失效将终止、容易实现服务质量和拥塞控制

## 路由算法

* 路由：确定该使用哪一条路径
* 转发：当一个分组到达时所采取的的动作
* 自适应算法：会根据拓扑结构和流量的变化改变路由决策
* 非自适应算法：不会根据当前测量或者估计的流量和拓扑结构，来调整它们的路由决策（静态路由）
* 会话路由：虚电路子网中路由，当建立虚电路时才需要确定路由路径

### 优化原则

* 最优化原则：如果路由器J在I到K的最优路径上，则J到K的最优路径也必定沿着同样的路由路径。
* 汇集树：从所有的源到一个制定目标的最优路径的集合构成以目标节点为根的树。

### 最短路径路由

* 跳数、物理距离、延迟
* Dijkstra标记算法：两个节点间最短路径的算法，初始时所有节点的标记（从源节点沿着当前已知的最佳路径到达该节点的距离）都是暂时的，当已经发现一个标记代表了最短可能路径的时候，标记被变为永久的（以后不再改变）

### 扩散算发

* 同样为静态的路由算法
* 每一个进来的分组都被发送到除了进来的那条路线之外的每一条输出线路上。
* 抑制扩散过程
+ 分组头包含跳计数器，初始值等于源于目标间路径长度或最坏情形下的长度（子网直径）
+ 分组头包含序列号，让路由记录已经被扩散过的分组
+ 选择性扩散：只输出到大概方向正确的线路上
* 扩散法并不实用，但其高度健壮性可用于军事用途

### 距离矢量路由

* 属于动态的路由算法
* 每个路由器维护一张表（即一个矢量），列出已知目标的最佳距离及线路，通过与邻居交换信息不断更新
* Bellman-Ford 路由算法、Ford-Fulkerson算法
* 无穷计算问题：X告诉Y它有一条路径的时候，Y无法知道自己是否在这条路径上。每次更新列表，坏消息扩散一步，直至无穷大。

### 链路状态路由

路由器的工作分为5个部分

* 发现邻居节点：启动时发送HELLO分组给邻居，邻居以其网络地址应答
* 测量线路开销：发送ECHO分组，得到邻居节点的延迟
* 创建链路状态分组：包括发送方标识、序列号、年龄、邻居及其延迟列表
* 发布链路状态分组：扩散法
+ 序列号回转，采用32位序列号
+ 路由器崩溃，从0开始的下一分组将被作为重复分组而拒绝
+ 序列号破坏，将作为过时分组而拒绝
* 计算新的路由路径：获得所有链路状态分组后，运行Dijkstra算法构建出到所有可能目标的最短路径

另一路由状态协议是IS-IS（intermediate system-intermediate system，中间系统对中间系统），原用于DECnet、NSFNET骨干网、CDPD、Novell Netware（使用变种NLSP来路由IPX分组），后被ISO采纳为无连接网络层协议CLNP，后被多次修改，如IP协议。

OSPF采纳了IS-IS，但IS-IS编码方法支持携带多个网络层协议的信息，二OSPF不具备这样的特性。

### 分级路由

路由器被划分为区域（region），区域被组织为群（cluster），群被组织为区（zone），区被组织为组（group）。路由器只知道自己所在区域的目标地址。

### 广播路由

* 广播：同时将所有目标发送一个分组
* 实现方法
+ 源机器给每一目标单独发送
+ 扩散法
+ 多目标路由：只给必要的路线发送
+ 汇集树
+ 逆向路径转发：如果通过常用发送分组的线路到达，则认为是第一份副本并转发

### 多播路由

* 只给一组目标发送，而不是发送给所有目标

### 移动主机路由

* 主场所：主机的永久性地址
* 外部代理：记录当前访问该区域的移动主机
* 本地代理：记录主场所在这个区域，当前正在访问其他区域的主机

### Ad Hoc 网络中的路由

* 每个节点包含一个主机和一个路由器，节点两两相邻，则成为Ad Hoc网络或MANET（mobile ad hoc networks，移动Ad Hoc 网络）
* AODV（ad hoc on-demand distance vector）路由算法：类似Bellman-Ford距离矢量算法
* 路径发现
* 路径维护：活动邻居

### 对等网络中的节点查询

* 节点标识符：IP地址的160位散列值
* 键：记录名字的160位散列值，该记录的索引关联信息保存在对应标识符的节点上
* successor(i)返回从i开始第一个实际节点的标识符
* 指取表：加快了搜索目标节点IP的过程

## 拥塞控制算法

### 通用原则

* 监视系统，检测何时何地发送了拥塞
* 将该信息传递到能够采取行动的地方
* 调整系统运行

### 拥塞预防策略

* 传输层：重传、乱序缓存、确认、流控制、确认超时
* 网络层：子网内部的虚电路与数据报、分组排队和服务、分组丢弃、路由算法、分组生存期管理
* 数据链路层：重传、乱序缓存、确认、流控制

### 虚电路子网中的拥塞控制

* 准入控制

### 数据报子网中的拥塞控制

每条线路关联一个变量 u新 = a u旧 + (1-a)f，a表示了路由器忘记历史有多快

* 警告位：位于分组头，分组到达目标端后，传输实体将警告位复制到下一确认分组，源主机因此削减流量
* 抑制分组：路由器直接给源主机送回一个抑制分组 （choke packet）
* 逐跳（hop-by-hop）抑制分组：影响沿途的每一跳，收到抑制分组的路由立即减慢该方向的分组（要求分配更多的缓冲区）

### 负载丢弃

* 随机的早期检测：RED（random early detection，随机的早期检测）算法，在恶化之前开始丢弃分组

### 抖动控制

每一跳都记录期望传输时间，到达晚了就尽快转发，否则多停留一段时间

## 服务质量

### 好的服务质量所使用的技术

* 过度提供资源
* 缓冲能力：接收方在递交数据前缓存起来
* 流量整形：在服务器段进行平滑处理；服务等级协定（承运商与顾客）、流量监管（对业务流进行监视）
* 漏桶算法：Turner（1986），常数服务时间的单服务器排队系统
* 令牌桶：每隔一段时间产生令牌，每送出去一个分组，计数器减一，到零时不再发送分组。令牌足够时以最大速度输出，此后为令牌产生速度
* 资源预留：带宽、缓冲区空间、CPU周期
* 准入控制
* 比例路由：分散流量到多条路径
* 分组调度：流之间公平排队、加权的公平排队

### 综合服务

* 基于流的算法或综合服务（RFC2205~2210）：流式多媒体的体系结构
* 资源预留协议（resource reservation protocol，RSVP）

### 区分服务

* 基于类别的服务质量（相对于基于流的服务质量）
* 快速型转发：另外的通道
* 确保行转发：确保不会丢弃分组

### 标签交换和MPLS

* MPLS（multiprotocol label switching，多协议标签交换）：RFC 3031，在数据链路层之上添加MPLS头
* MPLS与VC（虚电路）区别
* MPLS 将多个发往同一目标的分组组合起来（虚电路做不到）
* 建立转发表
* 虚电路：在建立连接时发送setup packet到网络中建立转发表
* MPLS：
* 数据驱动：分组到来时，联系下一跳生成这一分组流（FEC，forwarding equivalence class，转发等价类）的标签；使用有色绳索来避免环
* 控制驱动：路由启动时，检查哪些路由路径中自己是最终目标，然后为该路径建立FEC（forwarding equivalence class，转发等价类）并分配标签，将标签传递给邻居，传给所有的路由器

## 网络互联

* 多协议路由器
* 面向连接的网络互联：级联虚电路
* 无连接的网络互联：数据报模型
* 隧道技术：将IP分组插入WAN网络层分组净荷域中发送
* 互联网路由：内部网关协议、外部网关协议、自治系统（AS，autonomous system）
* 分段：每个网络会限制分组的最大长度

## Internet上的网络层

原则

* 保证它能够工作
* 尽可能使它简单
* 作出明确的选择
* 尽可能做到模块化
* 期望具备异构性
* 避免使用固定不变的选择和参数
* 寻找一个好的设计，它不必是最完美的
* 对于发送操作一定要严格，而对于接收操作要有一定的容忍度
* 要考虑伸缩性
* 要考虑性能和代价

### IP协议

* IPV4头：版本、IHL、服务类型、总长度、标识、DF、MF、分段偏移、生命期、协议、头部校验和、源地址、目的地址、选项

### IP地址

* 分类的编制方案（classful addressing）
+ A类：0+网络+主机；1.0.0.0~127.255.255.255
+ B类：10+网络+主机；128.0.0.0~191.255.255.255
+ C类：110+网络+主机；192.0.0.0~223.255.255.255
+ D类：1110+多播地址；224.0.0.0~239.255.255.255
+ E类：11110+保留将来使用；240.0.0.0~247.255.255.255
* 网络号管理：ICANN（internet corporation for assigned names and numbers）
* 点分十进制标记法
* 子网：通过子网掩码分别路由
* CIDR-Classless InterDomain Routing（无类别域间路由）：RFC 1519，将剩余的IP地址以可变大小块的方式进行分配，而不管它们所属的类别；聚集表项（用二进制地址与掩码标识一组IP地址）
* NAT-网络地址转换
* 为每个公司分配一个IP地址用于传输Internet流量；公司内部用每台计算机唯一的IP地址常用来传输内部流量。
* 三段保留的IP地址范围如下，包含这些地址的分组不应出现在Internet上
+ 10.0.0.0-10.255.255.255/8
+ 172.16.0.0-172.31.255.255/12
+ 192.168.0.0-192.168.255.255/16
* 操作方式：IP分组大多携带UDP或TCP净荷，从中提出目标端口和源端口进行一次转换，以TCP为例
+ 请求建立TCP连接时，替换TCP的源地址与源端口，替换IP与TCP头部校验和，建立源地址与源端口的表项（共65535个）
+ IP分组到达时，取出TCP的目标端口，查找对应的内部IP表项，替换目标端口与目标地址，替换IP与TCP头部校验和，转发给内部主机

### Internet 控制协议

* Internet 控制消息协议（ICMP，internet control message protocol）：报告Internet有关事件
* ARP-地址解析协议（address resolution protocol）
+ 要发送分组的主机首先发送一个广播分组到以太网络，询问IP对应的以太网地址，只有拥有该IP的主机以其以太网地址应答
+ 优化：1.缓存结果；2.机器启动时广播地址映射，请求查询自己的IP，检测有无冲突（应答）
* RARP（reverse address resolution protocol，反向地址解析协议）：机器启动时询问自己IP，RARP服务器送回它的IP。因受限的广播（全1的目标地址）不会被路由转发，每个网络都需要一个RARP服务器。
* BOOTP：RFC951、1048、1084，机器启动时使用UDP分组来询问自己IP。新加入的主机要系统管理员为它分配IP地址并加入BOOTP配置文件。
* DHCP（dynamic host configuration protocol，动态主机配置协议）：RFC 2131、2132，允许手工分配IP，也允许自动分配。也通过广播发送请求，每一网络有一DHCP中继代理（relay agent），主机先广播DHCP DISCOVER分组，DHCP中继代理单播给DHCP服务器，进而获得IP地址。租用：主机需在租用期到达之前申请续租，否则将释放其IP。

### OSPF-内部网关路由协议

* OSPF（open shortest path first）将每个AS划分为编号的区域（area），每个AS有一骨干网络（backbone area），编号为0.
* OSPF区分4种路由器：
+ 内部路由器：完全在一个区域内部
+ 区域边界路由器：连接两个或多个区域
+ 骨干路由器：位于骨干区域上
+ AS边界路由器：与其他AS中的路由器进行通信
* 邻接的：OSPF要求每个LAN中选举出一台指派路由器（designated router），该路由器与该LAN上所有其他路由器都是邻接的

### BGP-外部网关路由协议

* BGP（border gateway protocol）将网络分为三种：末端网络（与BGP图只有一个连接）、多连接网络（一般可用来传输中转流量）、穿越网络（愿意处理第三方分组，不过有限制条件）
* BGP路由间通过TCP连接通信

### Internet 多播

* IP通过D类地址来支持多播，要通过特殊的多播路由器
* IP支持两种组地址
+ 永久地址
* 224.0.0.1 一个LAN上的所有系统
* 224.0.0.2 一个LAN上的所有路由器
* 224.0.0.5 一个LAN上的所有OSPF路由器
* 224.0.0.6 一个LAN上的所有指派路由器
+ 临时组：进程要求主机加入或离开某个组，主机记录它的进程属于哪个组
* 查询和应答分组使用IGMP（internet group management protocol）协议

### 移动IP

* 可通过主动ARP（gratuitous ARP）更新路由器的映射缓存
* 外部代理通过定时发送广告分组（advertisement）来通知新进入的主机

### IPv6

* IPv6为IEEE Network发表的SIPP（simple internet protocol plus，增强的简单Internet协议）
* IPv6头部：版本、流量类别、流标签、净荷长度、下一个头、跳数限制、源地址、目标地址
* 扩展头部：为兼容IPv4，跟在固定头部的后面（可以有多个）
* 16字节固定长度编址

# 传输层

## 传输服务

### 向上层提供的服务

* 传输实体：传输层内部，利用网络层提供的服务，向它的用户提供高效、可靠和性价比合理的服务的硬件/软件
* 传输服务提供者、传输服务用户

### 传输服务原语

* LISTEN、CONNECT、SEND、RECEIVE、DISCONNECT
* TPDU（transport protocol data unit，传输协议数据单元）：从传输实体发送到另一个传输实体的消息。

### 伯克利套接字（berkeley socket）

* Berkeley UNIX使用的TCP socket原语：SOCKET、BIND、LISTEN、ACCEPT、CONNECT、SEND、RECV、CLOSE

## 传输协议的要素

### 编址

* 为监听连接请求的进程定义相应的传输地址，Internet：端口（port）；ATM：AAL-SAP；一般术语：TSAP（transport service access point，传输服务访问点）
* 同样，网络层的端点称为NSAP（network service access point，网络服务访问点），IP为一个特例。
* 初始连接协议：采用进程服务器为那些较少使用的服务器提供代理功能（监听一组端口），请求到达时启动相应的服务器，继承与客户的连接。
* 名字服务器（目录服务器）：在特殊硬件运行，不能在用户通话时临时创建

### 建立连接

* 分组生存周期：受限制的子网设计、分组设置跳计数器、分组时间戳
* TPDU编号，相等编号的TPDU不会同时有效，序列号空间应足够大，序列号回绕时同样编号的TPDU都已经消失

### 释放连接

* 两军队问题

### 流控制和缓冲

### 多路复用

* 向上多路复用：传输实体将TPDU交给上层指定的进程
* 向下多路复用：将流量分布到多个网络连接

### 崩溃恢复

## 有限状态机描述传输协议

## Internet 传输协议-UDP

### UDP介绍

* UDP（User Datagram Protocol，用户数据报协议）数据段由8字节头和净荷域构成。
* UDP头：源端口、目标端口、UDP长度、UDP校验和

### 远过程调用

* RPC（remote procedure call，远过程调用）：让远程调用像本地过程调用一样，客户程序需要绑定一个小的库过程（客户存根），服务器程序绑定一个服务器存根。
* 参数包装：列集（marshaling）

### 实时传输协议

* RTP（real-time transport protocol，实时传输协议）：RFC 1889
* 用户空间（多媒体应用->RTP）->套接字接口->操作系统内核（UDP->IP->以太网）
* RTCP（realtime transport control protocol，实时传输控制协议）：处理反馈、同步和用户界面等。

## Internet 传输协议-TCP

* TCP（transport control protocol，传输控制协议）：在不可靠的互联网络提供一个可靠的端到端字节流。
* TCP服务模型：16位端口，1024以下为知名端口
* 守护进程（unix中称inetd，internet daemon）：同时关联到多个端口，连接进入时fork出新的进程
* 紧急数据：URGENT标记
* TCP数据段（TCP segment）；MTU（maximum transfer unit，最大传输单元），以太网通常为1500字节净荷。
* TCP数据段（包括20字节的头）：源端口、目标端口、序列号、确认号、TCP长度、URG、ACK、PSH、PST、SYN、FIN、窗口大小、校验和、紧急指针、可选项、数据
* TCP连接的建立：SYN(SEQ=x)->SYN(SEQ=y, ACK=x+1)->SYN(SEQ=x+1, ACK=y+1)
* TCP传输策略：Nagle算法，数据进入发送方后只发送第一字节，其后的字节缓冲起来，直到第一字节被确认为止。
* TCP拥塞控制：网络容量（拥塞窗口）、接收方容量（接收方准许窗口）、慢启动法、阈值
* TCP定时器管理：重传定时器、持续定时器（确认超时的探询消息）、保活定时器（一段时间后发送，对方不应答则终止连接）
* 无线TCP和UDP：间接TCP、同质的网络
* 事务型TCP：用UDP来实现RPC的高效率，用TCP实现可靠性，T/TCP（transaction TCP，事务型TCP）；SCTP（stream control transmission protocol，流控制传输协议）

## 性能问题
广播风暴、带宽-延迟乘积

### 网络性能的测量

* 确保样本空间足够大
* 确保样本具有代表性
* 使用粗粒度时钟时要谨慎
* 确保在测试过程中不会发生不可预知的事情
* 缓存机制可能会破坏测量的正确性
* 理解所测量的指标
* 在往外推广结果时要谨慎

### 具有更好性能的系统设计

* CPU速度比网络速度更加重要
* 减少分组的数量可以减少软件开销
* 使环境切换的次数减到最少
* 使复制操作的次数减到最少
* 可以购买更多的带宽，但无法要求更低的延迟
* 应该想办法避免拥塞，而不是从拥塞中恢复
* 避免超时

### 快速的TPDU处理

* 分离出正常的发送操作病对它们作特殊处理

### 针对千兆网络的协议

旧的协议面临的问题

* 32位序列号：对于1Gbps的以太网，一轮序列号回绕时间为34s，大于internet上最大分组生存周期120s
* 通信速度的提高比计算速度的提高快得多
* 如果一条线路的带宽-延迟乘积非常大，则回退n步协议的性能会非常差
* 千兆位线路本质上不同于1兆位线路，因为长的千兆位线路的主要制约因素是延迟，而不是带宽
* 对于许多千兆位应用，分组到达时间的偏差与平均延迟本身一样重要


# 应用层

## DNS-域名系统

* DNS（Domain name system）：RFC 1034、1035，调用解析器（resolver）将名字映射成IP地址

### DNS名字空间

* DNS名字空间：internet被分为200多个顶级域，每个域被分为若干子域，子域又被进一步划分，以此类推。
* 顶级域有两种：通用域和国家域
+ 通用域包括com（商业的）、edu（教育性机构）、int（国际性组织）、mil（美国军队）、net（网络供应商）、org（非营利性组织）、biz（商贸）、info（信息）、name（人们的名字）、pro（职业）、aero（航空业）、coop（合作社）、museum（博物馆）
+ 国家域定义在ISO 3166中。

### 资源记录

* 每个域都有一组与它相关联的资源记录；当解析器把域名传递给DNS时，DNS所返回的是与该域名相关联的资源记录。
* 每条资源记录是一个5元组：Domain_name（域名）、Time_to_live（生存期）、class（类别）、type（类型）、value（值）

### 名字服务器

* 权威记录：来自于管理该记录的权威机构，因此总是正确的
* 递归查询：当解析器接收到一个域名查询时，它将该查询传递给本地的一个名字服务器，如果被查询域名落在该名字服务器的管辖范围内，那么返回权威的资源记录；如果本地没有关于它的信息，那么本地名字服务器向顶级名字服务器发送一条查询此域的消息。
* LDAP（lightweight directory access protocol，轻量级目录访问协议）：RFC 2251，定位到一般的对象，如人员、资源、服务等。

## 电子邮件

### 结构与服务

* 用户代理：阅读和发送电子邮件
* 消息传输代理：将消息从源端传送到目标端
* 电子邮件基本功能 
+ 撰写
+ 传输
+ 报告
+ 显示
+ 处理

### 消息格式

* RFC 822：基本ASCII电子邮件
* 头域：To、Cc、Bcc、From、Sender、Received、Return-Path、Data、Reply-To、Message-Id、In-Reply-To、References、Keywords、Subject
* MIME-多用途Internet邮件扩展
+ 头域：MIME-Version、Content-Description、Content-Id、Content-Transfer-Encoding、Content-Type
+ 二进制消息编码（base64编码，又称ASCII盔甲）：0-63分别为A-Z、a-z、0-9、+、/；==与=分别代表一个组只含8位或者16位；对少量非ASCII字符的消息编码效率较低
+ 可打印的引用编码（quoted-printable encoding）：7位的ASCII编码，所有超过127的字符被编码为等号+2个用16进制数字表示的字符值。

### 消息传输

* SMTP（simple mail transfer protocol，简单邮件传输协议） 
+ 在25号端口建立TCP连接
+ 命令：HELLO、MAIL FROM、RCPT TO、DATA等
+ ISP服务器上运行消息传输代理，接收邮件
* POP3（post office protocol version 3，邮局协议第三版）
+ 在110端口建立TCP连接
+ RFC 1939，用户从ISP的消息传输代理获得电子邮件
+ 假设用户每次交互后清除邮箱后脱机工作
* IMAP（internet message access protocol，Internet 消息访问协议）
+ 在143端口建立TCP连接
+ 假设用户的邮件会永久地保存在服务器上
* 投递特性：过滤器、假期守护程序（自动回复）
* webmail

## 万维网

### 结构概述

* URL（unform resource locator，统一资源定位符）：命名web页面
+ 组成：协议（也称方案，scheme）+页面所在机器的DNS名字，唯一指定特定页面的本地名字
+ 协议类型：http（hypertext transfer protocol，超文本传输协议）、ftp、file、news（NNTP，network news transfer protocol，网络新闻传输协议）、gopher、mailto、telnet
+ URN（universal resource name，通用资源名）：RFC 2141，不指定页面所在位置就能够引用页面，可减轻服务器负载
* 客户端
+ 浏览器运行步骤
* 确定URL
* 查询DNS以确定IP
* 与IP的80端口建立TCP连接
* 发送请求以获取URL指向的文件
* 服务器发送文件，释放TCP连接
* 浏览器显示文件中的文本，取回并显示图片
* 浏览器扩展
+ 插件：代码模块，浏览器从磁盘取出，安装称自己的一个扩展模块，运行在浏览器内部，完成工作后从浏览器内存中移除掉
+ 辅助应用程序：完整的应用程序，作为独立的进程来运行，接受临时文件的名字来打开文件
* 服务器端
+ 服务器运行步骤 
* 接收来自客户（浏览器）的TCP连接
* 获取所需文件名
* 从磁盘获取文件
* 将文件返回给客户
* 释放TCP连接
+ 服务器场（server farm）
* 组织：前端连接到一个LAN中，LAN中有一个路由器和若干处理节点（独立的计算机）
* TCP移交（TCP handoff）：避免所有请求与回复都通过前端
* 无状态特性与cookie
+ RFC 2109：当用户请求web页面时，可以提供附加信息cookie（最大4k）
+ cookie域：域名、路径、内容、过期时间、安全
+ 非持久的cookie：没有包含过期时间域，浏览器退出时丢弃
+ 持久的cookie：包含过期时间域

### 静态web文档

* HTML（hypertext markup language，超文本标记语言）
* 表单
* XML（extensible markup language，可扩展标记语言）
* XSL（extensible style language，可扩展样式语言）
* SOAP（simple object access protocol，简单对象访问协议）：应用之间执行RPC（远过程调用）的方法，以XML构造请求，以HTTP发送
* XHTML（extended hypertext markup language，扩展的超文本标记语言）：用于小型移动设备，语法更挑剔

### 动态web文档

* 服务器端动态web页面生成（动态html）：CGI（common gateway interface，公共网关接口）、PHP（hypertext preprocessor，超文本预处理器）、JSP（javaserver pages，java服务器页面）、ASP（active server page，活动的服务器页面，ms版的php和jsp）

* 客户端动态网页生成：javascript、applet（jvm上运行的java小程序）、activeX控件（ms）

### HTTP-超文本传输协议

* 连接：HTTP1.0服务器回应后关闭TCP连接；HTTP1.1支持持续连接
* 方法：GET、PUT、HEAD、POST、DELETE、TRACE、CONNECT、OPTIONS
* 消息头：请求头、回应头

### 性能增强

* 缓存、代理（维护缓存）
* 服务器复制：镜像、瞬间拥挤
* 内容分发网络：CDN（content delivery network），图像、音频等大文件存储在CDN上

### 无线web

* WAP（wireless application protocol，无线应用协议）使用新的HTML标准，9600bps，协议层
+ 无线应用环境（WAE)
+ 无线会话协议（WSP）
+ 无线传输协议（WTP）：代替TCP，效率原因
+ 无线传输层安全（WTLS）
+ 无线数据包协议（WDP）：类似UDP
+ 承载层（GSM、CDMA、D-AMPS、GPRS等）
* I-Mode（information-mode，信息模式）
+ 对语音信号使用电路交换网络，对数据信号使用分组交换网络
+ 数字网络基于CDMA，手持机使用LTP（lightweight transport protocol，轻量级传输协议）并通过空中链路与协议转换网管通话
+ 软件结构
* 用户交互模块
* 插件+cHTML（compact HTML，紧凑的HTML）解释器+Java
* 简单的窗口管理器
* 网络通信
* 实时操作系统
* 第二代无线web
+ 新特新
* 推模型和拉模型
* 运行将电话集成到应用中
* 多媒体信息
* 264个象形文字
* 存储设备接口
* 浏览器插件
+ wap2.0支持两种协议栈
* XHTML
* WSP HTTP
* WTP TLS
* WTLS TCP
* WDP IP
* 承载层 承载层

## 多媒体

### 音频压缩

* MP3（mpeg audio layer 3，MPEG音频层3）
* 波形编码：使用较少的傅里叶分量重现波形
* 感知编码：利用心理声学的频率屏蔽和暂时屏蔽去掉某些分量

### 流式音频
* 元文件：将整个音频分为很多元文件，减少缓冲时间
* RTSP（real time streaming protocol，实时流协议）：管理用户界面、处理传输错误、解压缩音乐、消除抖动
* 拉式服务器、推式服务器、低水印标记和高水印标记

### IP 语音

* H.323：ITU在1996年发布，终端、网守、区域。、H.245（新的压缩算法）、H.225（与网守通信）
* SIP（session initiation protocol，会话发起协议）

### 视频简介

* 一帧：一次扫描
* 隔行扫描与逐行扫描
* 彩色电视系统：SECAM（SEquentiel couleur avec memire，顺序与存储彩色电视系统）、PAL（phase alternating line，逐行倒相制式）、NTSC（national television standards committee，国家电视标准委员会）；亮度、色度
* HDTV（high definition television，高清晰度电视）
* 数字系统

### 视频压缩

* JPEG（joint photographic experts group，联合图像专家族）标准
+ 块准备：四像素取平均值（亮度比色度更敏感）
+ 对每一块作DCT（discrete cosine transformation，离散余弦变换）
+ 量化：将上一步的每个格点乘以对应的权值
+ 减小每一块的(0,0)元素值（DC分量），其他元素称为AC分量
+ 行程编码：同样的值用计数值表示
* MPEG（motion picture experts group，运动图像专家组）标准，MPEG-1与JPEG的区别在于运动补偿，包括四种帧
+ I（帧内编码，intracoded）：JPEG编码的静止图片
+ P（预测，predictive）：与前一帧之间的逐块差值
+ B（双向，bidirectional）：与前一帧和后一帧之间的差值
+ D（DC编码，DC-coded）：用于快进的快平均值

### 视频点播

* 准视频点播：在多个频道以某种时差播放同样的视频
* 线路：视频服务器->光纤->ATM或SONET骨干网络->光纤->交换机->区域分布式网络->消费者房子->机顶盒
* 视频服务器
+ Zipf定律：最受欢迎的那部电影，它的受欢迎程度是第七受欢迎电影的7倍
+ 分层存储：RAM->磁盘->DVD->磁带
+ 磁盘存储
* 磁盘场（disk farm）：每个驱动器存储一定数量的电影，有重复
* 磁盘阵列（disk array）或RAID（redundant array of inexpensive disks，廉价磁盘冗余阵列）：每部电影分布在多个驱动器上（条状化，striping）
* 分发网络：数据源与目标之间交换机和线路的集合
+ ADSL
+ FTTC（fiber to the curb，光纤到路边）
+ FTTH（fiber to the home，光纤到户）
+ HFC（hybrid fiber coax，混合光纤同轴电缆）

### Mbone（multicast backbone，多播骨干网）

* Mbone是internet之上的一个虚拟层叠网络
* 由隧道连接的多个多播岛组成，每个岛有至少一个mrouter（multicast router，多播路由器）
* 使用基于Bellman-Ford距离矢量算法的路由算法DVMRP（distance vector multicast routing protocol，距离矢量多播路由协议）
* PIM（protocol independent multicast，协议无关多播）：AS间的路由，IETF工作组开发

# 网络安全

## 密码学简介

* 加密：明文经密钥为参数的函数变换，输出密文
* 密码编码学、密码分析学、密码术
* Kerckhoff原则：所有算法必须是公开的，只有密钥是保密的
* 含糊的安全性（security by obscurity）：使算法保持秘密
* 工作因子：密码分析者面对的密钥的复杂性，对于穷举搜索，为密钥长度的指数量级
* 密码分析问题
+ 只有密文
+ 已知明文（有了一些相匹配的密文和明文）
+ 选择明文（能够加密一些自己选择的明文）

### 置换密码

* 保留明文字符顺序，进行明文伪装
+ 凯撒密码（单字母表置换）
* 字符频率猜测

### 转置密码

* 重新排序，不伪装明文
* 字符频率不变

### 一次一密

优点，不可能被破解；缺点，密钥数量限制、密钥流失、丢失字符。

* 量子密码系统：BB84协议
+ 定义
* 直线基：垂直和水平滤波器
* 对角基：上述基旋转45度
+ 0与1：每一组基任意分配两个偏振方向为0和1
+ 过程
0. A与B通信，T在监听
1. A传送一次性密钥（长度略超过期望长度的2倍）给B，每一位随机选择一个基。
2. B使用随机的基接收每一位；
3. B告诉A自己使用的基。
4. A告诉B哪些是正确的；
5. A与B使用正确传输的位序作为密钥；
+ 反监听
1. 监听者的密钥不完整。监听者T，对于B基序列中能正确接收的部分，若T与B恰好使用相同的基，则T可以知道该位的密钥；否则T将丢失该位。可经过秘密放大进一步减少T知道的内容。
2. 监听检测。T必须将A的内容转发给B，却不能正确告知B的哪些基是正确的；一位密钥错误相当与B眼中的一位传输错误；A与B使用前向纠错码进行纠错，发现错误率大大超过设备的期望；得知T的存在。
+ 本质
1. 光子遇到与自己偏振方向成45度的滤波器，会随机跳到其中一个且概率相等。
2. 光子不可复制


### 基本的密码学原则
1. 消息必须包含一定的冗余度：区分有效消息、检测信道
2. 需要采取某种方法对抗重放攻击：新鲜度、时间戳

## 对称密钥算法

* 块密码：接受一个n位的明文块作为输入，利用密钥把它变换成n为的密文块
* P盒：转置操作，混淆
* S盒：置换操作，扩散
* 乘积密码：一系列的S盒和P盒叠加起来

### DES（data encryption standard，数据加密标准）

* 明文按64位数据块的单元加密，生成64位密文，接受56位密钥，共19个步骤，16次迭代
* 三重DES：EDE（K1, K2, K1）模式，兼容了DES算法（只需让K1=K2）

### AES（advanced encryption standard，高级加密标准）

* NIST（national institute of standards and technology，美国标准和技术委员会）在1997年1月发起了密码学竞赛，新标准称为AES，要求
+ 必须是对称的快密码算法
+ 公开所有设计
+ 支持128位、192和256位密钥长度
+ 软件、硬件实现都是可能的
+ 算法必须是公有的
* Rijndael：与DES相同，仍使用置换和转置，多轮策略（轮数取决于密钥和块长度）；另外，所有操作都涉及整个字节

### 密码算法的使用模式
AES和DES本质上都是置换和转置操作，同样的明文会得到同样的密文

* ECB模式（electronic code book mode，电子代码薄模式）：分割明文，逐块加密。容易被替换某一块。
* 密码块链接模式：第一个块与随机IV（initialization vector，初始向量）异或，之后的明文块与前一密文块异或后加密，IV一起传输
* 密码反馈模式：逐字节加密，不必等64位数据块；密文只有一位偶然翻转，会波及到坏字节在寄存器中时的8个字节
* 流密码模式
+ 过程：用一个密钥加密一个初始向量生成一个输出块，同样的密钥加密这个输出块产生第二个输出块，以此类推；然后将明文与该密钥流异或得到密文
+ 优点：密钥流仅仅依赖于IV和密钥，不会受到传输错误的影响。
+ 缺点：重复使用（密钥，IV）对，会产生同样的密钥流，会导致密文受到密钥流重用攻击（keystream resuse attack）
* 计数器模式：除密码薄模式以外的模式中，要想随机访问密文是不可能的
+ 过程：初始向量加常数后进行加密，再与明文异或；每个新的数据块使初始向量递增1
+ 优点：文件中任何地方的块都可以直接解密
+ 缺点：重复使用（密钥，IV）对，会导致密文受到密钥流重用攻击

### 密码分析

* 差分密码分析（differential cryptanalysis）：观察少量位差异的明文产生的密文，有些位模式可能比其他位模式更容易出现，这种现象可以导致概率攻击。可用于攻击任何一种块密码算法。
* 线性密码分析（linear cryptanalysis）：将明文与密文特定位异或，应该一半为0一半为1，而加密过程会引入偏差，这样的偏差总可以降低工作量。只需2^43个已知密文就可以破解DES。
* 电子功率消耗分析：计算机高电压表示1，低电压表示0，减慢时钟，记录CPU功率
* 时间分析：if语句的then和else执行时间不同时，减慢时钟可以推断出轮密钥。

## 公开密钥算法

加密算法E与解密算法D满足：

* D(E(P)) = P
* 从E推断出D极其困难
* 用选择明文攻击不可能破解E

### RSA
RSA算法建立在分解大素数的基础上，RSA分别为三位发现者名字的首字母

* 计算参数
+ 选择两个大素数p、q（典型情况为1024位）
+ 计算n=p*q和z=(p-1)*(q-1)
+ 选择一个与z互素的数d
+ 找到e使其满足e*d=1%z
* 加密
+ 公钥对为(e, n)
+ 将明文分块，每个明文P落在0<=P<n中
+ 计算C=P^e(mod n)
* 解密
+ 私钥对为(d, n)
+ 计算P=C^d(mod n)
* 使用：所有人公开自己的加密密钥E，B给A发送Ea(P)，A获得后进行解密P=DaEa(P)

### 其他的公开密钥算法

* 主要有两方面的算法
+ 分解大数的困难度
+ 以大素数为模来计算离散对数的困难度
* 背包算法：“根据给定的总重量找出可能的物品明细列表”被认为是计算上不可行的。该算法与其加强算法相继被S和R破解。
* 其他：计算离散对数的困难度、基于圆锥曲线

## 数字签名

数字签名应满足条件

* 接收方可以验证发送方所宣称的身份
* 发送方以后不能否认该消息的内容
* 接收方不可能编造这样的消息

### 对称密钥签名

选择一个中心权威机构BB，每个用户选择一个秘密密钥亲手交给BB。A发送A, Ka(B, Ra, t, P)给BB，BB将Kb(A, Ra, t, P, K_BB(A, t, P))给B

### 公开密钥数字签名
1. 假设公开密钥算法不仅满足D(E(P))=P，还满足E(D(P))=P
2. A向B发送 C=Eb(Da(P))
3. B得到明文 P=Ea(Db(C))

### 消息摘要
+ 特性
	* 给定P，很容易计算MD(P)
	* 给定MD(P)，想得到P是不可能的
	* 给定P的情况下，没有人能得到满足 MD(P')=MD(P) 的P'
	* 输入明文即使只有1位变化，也会导致不同输出
+ 加密摘要比明文快的多，可以加速数字签名算法
+ MD5
	* 将明文填补到448位
	* 消息后追加其消息长度（64位整数），此时共512位
	* 取出一个512字节的输入块，通过正弦函数与128位的缓冲区混合，每个输入块执行4轮
	* 128位的缓冲区即为最终的消息摘要
+ SHA-1（secure hash algorithm 1）：同样按照512字节块处理数据，唯一不同的是生成160位的消息摘要
	* 利用SHA-1和RSA对非保密的消息进行签名：Alice->明文P->SHA-1->P的散列值H->RSA(私钥Da)->签过名的散列值Da(H)->Bob

### 生日攻击
n个输入和k个可能的输出之间存在某种映射关系，公有n(n-1)/2个可能的输入对，若n(n-1)/2>k，则至少有一个匹配的机会是非常大的

## 公钥的管理

### 证书
CA（certification authority，证书权威机构），避免了24小时在线的密钥分发中心

* 生成证书
* Alice到CA，出示其公钥和身份，请求证明他的公钥
* CA给Alice一个证书，其中包括Alice的身份、CA的私钥对身份散列值的签名
* 证书验证
* Bob计算Alice身份的散列值，与CA的公钥应用在Alice证书的签名上得到的散列值进行比对，因Trudy无法得知CA的私钥，所以他不能对散列值正确地签名
* 证书格式标准 X.509：ITU1988年通过，采用OSI ASN.1（abstract syntax notation 1，抽象语法标记1）编码

### PKI（public key infrastructure，公开密钥基础设施）

* 信任链（证书路径）：分层的CA，顶级CA负责证明次级CA（又称RA，regional authority，区域权威机构），次级CA负责证明第三级CA，以此类推
* 信任锚：浏览器预先安装100多个根的公钥
* 目录（在哪里存放证书）：用户自己存放、DNS服务器存放
* 撤销：CA定期发布CRL（certificate revocation list，证书撤销列表）

## 通信安全

### IPSec
* RFC 2401、2402和2406，总是要求加密功能，但允许空算法
* IPSec是一个多服务、多算法和多粒度的框架
* 两种模式
+ 传输模式：直接插在IP头的后面
+ 隧道模式：整个IP分组封装到一个新的新的IP分组中，新分组具有全新的IP头

### 防火墙
防火墙包括两部分

* 分组过滤器（网络层）：配置了某些额外功能的标准路由器，负责检查进入和出去的所有分组
* 应用网关（应用层）：根据头、消息长度，甚至内容决定转发或丢弃

DoS（denial of service）攻击：向目标机器发送大量合法的分组，防火墙不能处理；DDoS（distributed denial of service）攻击：大量普通用户的机器被控制而进行DoS攻击

### VPN（virtual private network，虚拟私有网络）
建立在公共网络上的层叠网络，可利用IPSec实现隧道，将任意两个办公室的流量聚集到一个支持认证和加密功能的SA上

### 无线网络安全

* 802.11安全性：WEP（wired equivalent privacy，相当于有线网络的保密性）为数据链路层安全协议，使用基于RC4的流密码算法
* 蓝牙安全性：物理层的调频机制提供了一定程度的安全性；设备预先建立好的共享的秘密密钥（passkey，总密钥）；蓝牙的加密算法使用叫做E0的流密码，完整性控制使用SAFER+，两者都是对称密钥快密码算法
* WAP2.0安全性：它是基于IP的，可以使用IPSec；传输层可以使用TLS提供保护。

## 认证协议

### 基于共享秘密密钥的认证

* 质询-回应协议：容易受到反射攻击

### 建立一个共享密钥：Diffie-Hellman密钥交换协议

* 基于大素数分解的困难度，容易受到水桶队列攻击（又称中间人攻击）

### 使用密钥分发中心的认证协议

* 重放攻击
* Needham-Schroeder认证协议

### 使用Kerberos的认证协议

应用在许多实际系统中，如windows2000

### 使用公开密钥密码学的认证协议

## 电子邮件安全

### PGP（pretty good privacy，相当好的隐私）
* PGP使用一个称为IDEA（international data encryption algorithm）的块密码算法来加密数据
* 私钥环：一个或多个本人的公-私钥对
* 公钥环：与当前用户进行通信的其他用户的公钥

### PEM（privacy enhanced mail，增强隐私的邮件）

像PGP一样，每条消息都使用一次性密钥进行加密，密钥（被RSA或三重DES保护）也被包装到消息中

### S/MIME（Secure/MIME，安全的MIME）
* IETF提出

## Web 安全

### 安全的命名机制
* DNS欺骗
* 安全的DNS
* 自证明的名字

### SSL（secure sockets layer，安全套接字层）
在两个套接字之间建立安全的连接，位于应用层与传输层之间

* 客户与服务器之间的参数协商
* 客户与服务器的双向认证
* 保密的通信
* 数据完整性保护

### 移动代码安全

* java applet安全：解释器将其封装到沙箱一边限制它的行为
* Active控件：代码签名，认证码
* javascript：没有正式的安全模型
* 病毒：具有繁殖能力，不断复制自己

## 社会问题

###隐私
* clipper chip（剪切芯片）
* key escrow（密钥托管）
* 电子边境基金会（electronic frontier foundation）
* 匿名邮件中继器（anonymous remailer）
* 翻译型的邮件中继器（cypherpunk remailer）

### 言论自由

* 信息隐藏学（steganography）
* 数字水印

###　版权

* 版权（copyright）是对IP（intellectual property，知识产权）的创造者的一种授权
* 合理使用原则（fair use doctrine）
* TCPA（trusted computing platform alliance，可信计算平台联盟）

# 以太坊智能合约和DApp开发指南

- <a href="#想知道以太坊是什么">想知道以太坊是什么</a>
	- <a href="#白皮书">白皮书</a>
	- [官方网站](https://www.ethereum.org/)

- <a href="#想用以太坊钱包收发ether">想用以太坊钱包收发ether</a>

- <a href="#想安装、运行和使用以太坊节点（geth）">想安装、运行和使用以太坊节点（geth）</a>

- 想挖矿

- 想开发以太坊应用（包含智能合约的以太坊DApp）
	- 开发环境搭建
	- 学习solidity语言以开发智能合约
	- 学习开发框架(truffle)以提高开发效率
	- web3.js接口
	- 安全
	- 项目示例
	- 工具

- 想探索以太坊的应用
	- 应用

- 想了解以太坊是怎么实现的

	- 黄皮书 @todo
	- 源码剖析

- 想持续跟踪以太坊的进展

- 想知道学习以太坊知识的好的信息源有哪些
	- 官方文档


## <a name="想知道以太坊是什么">想知道以太坊是什么</a>

### <a name="白皮书">白皮书</a>

阅读白皮书，可以从『高层视角』了解以太坊的设计，可了解的信息包括：设计的初衷、设计思路、以太坊的核心特性。

地址：

- [以太坊白皮书](https://github.com/ethereum/wiki/wiki/White-Paper)
- [以太坊白皮书中文翻译版](https://github.com/ethereum/wiki/wiki/%5B%E4%B8%AD%E6%96%87%5D-%E4%BB%A5%E5%A4%AA%E5%9D%8A%E7%99%BD%E7%9A%AE%E4%B9%A6)

我的笔记：

以太坊是一个内置图灵完备语言的、用来编写智能合约的区块链。

- 语言：图灵完备，可以用来编码任意状态转换，而不仅仅是智能合约，智能合约只是状态转换中的一种。不过智能合约目前是最主要的一种状态转换。
- 智能合约：根据事先任意制订的规则来自动转移数字资产的系统。

核心特性：

- 账户
	- 账户可以包含：随机数、以太币余额、合约代码、存储
	- 外部账户：人们可以通过创建和签名一笔交易从一个外部账户发送消息
	- 合约账户：合约账户收到一条消息，合约内部的代码就会被激活，允许它对内部存储进行读取和写入，和发送其它消息或者创建合约
- 消息和交易
	- 消息：
	- 交易：存储从外部账户发出的消息的签名数据包。交易包含消息的接收者、用于确认发送者的签名、以太币账户余额、要发送的数据和两个被称为STARTGAS和GASPRICE的数值。
	- 消息和交易有什么不同：@todo 很像，讲不大清楚

- 状态转移
	- 账户集合构成状态
	- 交易使状态发生变化

- 代码执行
	- 计算状态可由一个简单的元组定义

- 区块链和挖矿
	- 最后一个区块，存储了链的全局状态


## <a name="想用以太坊钱包收发ether">想用以太坊钱包收发ether</a>

- 全节点钱包mist

mist是以太坊的官方全节点钱包。全节点，指钱包包含了以太坊的节点，钱包运行时，节点也运行。钱包的功能，要能使用，节点必须先同步以太坊网络的区块链数据（@todo 待确认是否必须同步），这往往是一个比较漫长的过程，并且磁盘容量必须大于区块链数据量。

[mist下载地址](https://github.com/ethereum/mist/releases)

- 轻量钱包

轻量钱包不需要运行以太坊节点。它通过连接其他以太坊节点，来实现ether的收发。（@todo 原理是否有别与btc的spv钱包）

市面上可供选择的轻量钱包包括：

- [imToken](https://token.im/)

## <a name="想安装、运行和使用以太坊节点（geth）">想安装、运行和使用以太坊节点（geth）</a>

如果需要全面的geth使用说明，参考:[geth官方wiki](https://github.com/ethereum/go-ethereum/wiki)

以太坊的官方文档也有一章讲geth使用：[Connecting to the Network](http://www.ethdocs.org/en/latest/network/connecting-to-the-network.html)

以下只覆盖基本的部分，如需了解如何使用geth进行以太坊账户管理、部署和调用智能合约、收发ether、发送交易，请参考以上链接。

- 安装geth

以太坊提供二进制geth包，去官网下载解压放到某个路经即可。

[geth下载地址](https://github.com/ethereum/go-ethereum/releases)

为了方便使用，可以放到path中，比如：把下载后，解压出二进制geth，并创建软连接：```ln -s /path/to/geth /usr/local/bin/geth```

最后运行```geth -h```，如果出现帮助说明，则安装成功。

- 运行geth

运行geth并打开console(option参数可改或可省略，含义见geth官方wiki)：

```geth --cache=256 --datadir "/home/data/.ethereum" console 2>/dev/null```

后台运行geth:

```nohup  geth --cache=256 --datadir "/home/data/.ethereum" 2>>log.20170830 &```

连接正在运行的geth并打开console(ipd地址要改成实际的):

```geth attach ipc:/home/data/.testnet2/geth.ipc``` 

- 使用geth

在geth console，可以向geth发送命令，包括一些了解网络状况等命令。

geth是否在监听：```net.listening```
peer数目：```net.peerCount```
peer信息：```admin.peers```
本节点信息：```admin.nodeInfo```

## 官方文档

地址：

- [以太坊官方文档](http://www.ethdocs.org/en/latest/)

官方文档详细介绍了以太坊节点的运行、管理，挖矿，智能合约和DApp的开发。

注意：这个文档，有些部分有些混乱和过时。

## 节点运行和管理

- geth

- 网络管理

- 搭建私有网络


## 开发环境搭建

- remix

	- [remix地址](https://remix.ethereum.org/)
	- [remix文档地址](https://remix.readthedocs.io/en/latest/)

## 学习solidity语言以开发智能合约

目前，以太坊的智能合约开发语言是solidity，要写智能合约，需要学会solidity。

- [solidity官方文档](https://solidity.readthedocs.io/)

以上文档已经很详细了，本文不重复发明轮子重新写一遍详细的语法说明。而是尝试从高层概括solidity的特性，以及梳理solidity中容易导致疑惑的地方。

内容：

- 高层视图
- 类型
- data location
- assignments behave
- visibility
- function修饰


## 学习开发框架(truffle)以提高开发效率

名为框架，但实际上，truffle并不是一个运行时框架，而是一个可以提高开发过程效率的工具。

使用truffle确实可以提高开发效率，但也引入了一层间接，使开发人员在一些地方会有困惑。有利有弊，权衡着用。

- [truffle官方网站](http://truffleframework.com/)
- [truffle官方网站文档](http://truffleframework.com/docs/)
- [宠物店例子](http://truffleframework.com/tutorials/pet-shop)

学习内容：

- 安装
- 创建项目
- 编辑器
- 选择节点
- 编译
- 部署
- 测试
- 复用包
- 调试
- 一个实例

@todo

## 项目示例

- helloworld
- love lock (@todo)
- erc20

## 工具

- MetaMask

## 应用

- [白皮书中提到的应用](https://github.com/ethereum/wiki/wiki/%5B%E4%B8%AD%E6%96%87%5D-%E4%BB%A5%E5%A4%AA%E5%9D%8A%E7%99%BD%E7%9A%AE%E4%B9%A6#%E5%BA%94%E7%94%A8)




# 以太坊智能合约和DApp开发指南

- <a href="#想知道以太坊是什么">想知道以太坊是什么</a>
	- <a href="#白皮书">白皮书</a>
	- [官方网站](https://www.ethereum.org/)

- 想使用以太坊，节点，钱包
	- 节点运行和管理

- 想挖矿

- 想开发智能合约和DApp
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




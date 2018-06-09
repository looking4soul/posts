# ETC分析

## 分析内容

从基本功能入手，分析ETC目前能做什么、有什么。

通过分析ETC正在进行的子项目，了解ETC其发展方向。

通过了解ETC背后的团队，了解其大概的技术实力。

## 现状

- 能做什么
	- 和eth一样，是一个智能合约平台
	- 和eth不一样的是，在2016年的分叉后，etc并不具备eth后来的功能

- 网络状态
	- 交易数：最近10个block平均值：0.6每block（作为对比，eth是158），历史平均值：4.67每block（作为对比，eth是41.7）
	- 算力：8962.16 GH/s（作为对比eth是266545.86 GH/s）,约30倍。(作为对比，eth/eth价格=37.6，算力比和价格比接近)

- 社区舆论
	- ？
	
## 项目

ETC正在进行子项目及其含义：

- Classic Geth：从ETH Geth中fork出来的，但目前已有50%的代码不一样了，专注于架构模块化，性能，改进，使其在商业环境更友好。从2018年的开发路线看，这个项目的目标集中在性能改进，而非功能增加，比如：Logging、Caching、Opcodes Compatibility、Address / Transaction Indexing、Syncing等。

- SputnikVM：嵌入式EVM。2018的目标在于速度，通过JIT来提升。

- Sidechains：让ETC具有支持IoT的扩展性。2018年的目标在于PoA。

- Emerald Platform：ETC区块链的SDK。

- Mantis: 显著性能提升，用scala写的全新节点客户端。

## 团队

- ETCDEV：地理分布，全职，10个技术人员左右，负责Classic Geth、SputnikVM、Emerald Platform、Sidechains。

- IOHK：数学和科学驱动的开发团队，负责Mantis，ETC只是其工作的项目之一。

- ETC COOPERATIVE：提供经济上的支持。

- ETC LABS：提供经费、行业连接、办公空间。

- Ethereum Commonwealth：维护Classic Ether Wallet。





# 技术开发英雄帖 Hero Wanted

本文档列出Jouleverse核心最关键的一些待开发的问题，或者待攻克的难题。欢迎各路英雄前来贡献代码！

TODO: 技术代码采取开源代码管理方法，借鉴参考bitcoin core，稍后整理相关文档

## 链代码

源代码repo: [jouleverse](https://github.com/Jouleverse/jouleverse) 【暂时仅core contributors可见】

maintainer: jiaolian

### 允许PoA记账节点指定不同于signer address的coinbase address用于接收gas收入

issue: 尚未创建

rationale: 由于Jouleverse的合规性要求，EOA地址中的原生Joule不可流转。目前记账节点只能用signer address (EOA)接收gas fee，从而导致作为gas收入的Joule被锁死在EOA地址里无法循环利用。

solution: 一个可能的解决方案是，允许记账节点在配置文件中指定一个其他地址，比如多签钱包地址，作为coinbase地址来接收gas收入的Joule。

### 允许任何人对PoA区块链实施硬分叉(hard fork)

issue: 尚未创建

rationale: Jouleverse PoA采取轮流签名出块，但是没有过半数记账节点的配合，无法硬分叉区块链。这使得记账节点的记账权无法被推翻，削弱了见证节点对记账节点的制衡。应当有一种办法，让见证节点（无需许可，人人可建立）可以有能力自由硬分叉区块链，从而抛弃既有的记账节点但保留某一区块高度之前的全部历史数据，继续为支持新分叉的社区提供服务。

solution: 目前还没有想到可行的方案。

## 治理

源代码repo: [governance](https://github.com/Jouleverse/governance)

maintainer: jiaolian

### 可移交控制权的Timelock

issue: 尚未创建

rationale: 锁定创世金库，实现2:8分治和线性释放模型不可变更。作为过渡，初期应允许多签控制，而后可以移交给Governance合约由治理（民主投票）控制。另外，需要像多签钱包那样执行任意调用数据的能力，但增加一个延时设定。

solution: 存在疑难点，需要推敲。

### 治理合约Governance

issue: 尚未创建

rationale: 需要一个治理合约来代替多签合约，由民主投票取代多签钱包，来对提案和Timelock拨款实施共同控制。

solution: 需要规划。

## 可信认证

源代码repo: [JTI 2.0](https://github.com/Jouleverse/jti2)

maintainer: jiaolian

### 分组数据上链

issue: 尚未创建

rationale: 方便链下数据-链上数据比对、连接，更好地进行数据统计。

### 组长赋标

issue: 尚未创建

rationale: 目前JTI赋标由一人承担，存在中心化瓶颈。应分布式进行。

solution: 责任组长赋分组标，另一组长核实后赋标。另设审计人员，后向审核JTI登记表，并有权撤销疑似不当的赋标。

## 区块浏览器

源代码repo: [explorer](https://github.com/Jouleverse/explorer)

### 修正交易详情页不准确的数字

issue: 尚未创建

rationale: 已确认交易应当显示tx receipt中实际消耗的gas量，而不是提交的gas预算量。

### 拆分合约工具，融入每一个合约地址的详情页里面去

issue: 尚未创建

rationale: 体验上会感觉更加去中心化，而不是有一个非常集中的页面入口。


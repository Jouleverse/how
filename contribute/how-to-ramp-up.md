# Jouleverse(焦耳宇宙)漫游指南

Author | 教链([evan.j](https://jscan.jnsdao.com/#/jns/evan.j)), XXX
-|-
Reviewer | -

## Jouleverse释义

Jouleverse 一词由国际公制能量单位 Joule(焦耳) 和 universe(宇宙) 的后缀 -verse 拼合而成。含义是焦耳宇宙或者能量宇宙。

狭义的 Jouleverse 是一个完全由社群驱动的、去中心化的、面向合规的、不发币的开放区块链。愿景是成为一个合规的web3基础设施，支持大量web3应用的繁荣生态。

广义的 Jouleverse 是一个包含链节点、大量web3应用、活跃的社群和用户(参阅下文“行星系统”)的完整的web3元宇宙。

## 什么是 J (Joule)

J (Joule) 是国际公制能量单位，也是Jouleverse的使用费——或者叫做燃料费（gas fee）——的计量单位。

要使用Jouleverse，就要消耗燃料（能量），就像使用云计算需要消耗资源费，开汽车需要消耗汽油一样。

Jouleverse高度兼容以太坊。其燃料费计算公式亦与后者相同：gas fee (J) = gas limit (unit) x gas price (gwei/unit) x 1/10^9.

Joule的发音是“焦耳”，点击听美式发音示范：

<audio controls>
  <source src="data:audio/mpeg;base64,//MoxAAJgFIUAUMQANAAASgYuAYGBvAgAIoAAHP/8EBoIDQff/yn//hgo7+rw//+UdwfegQ6EiWQ/2/X/z7H//n//5O8nf////MoxBUR0xqMAYJQAZOfH58f///nx+P3EWP3EX///+Lbg3g3k4AsQ5gBMfCwDX////+cSA1kRILZQkFtDBbCFf//f/////////MoxAgO+yLQAYEoAP//////+RvpZ3a+kzuahbI6DjTTuii6gICBQqUwW9+/+UXeQURiFHlF2jijRooGlVrHHiD/y/////////MoxAcO2r7gAcEoAf///////+vYh11c9bn1dkVBQw4XVgEE4dOITlOqGF1sZFopjuQgo4hQaZ3FDRne6Mw7+p+VAtoAtbbo//MoxAYNSjMl/hAEmv3CCCNun//qu7s+QqIRjqZqVRehKVq59GT0T8iqRkMQSYiLva5OjUFHJTu+24DUKv6OZX1qOJhXAPB0//MoxAsPaXLkymiElPJOWlG/0EW////7///7vMYyKFGOX0JFxYGgVMiMKPrdxFBkWCgdewXDVVqF8rur7cRRFf2Pk8IyBLSO//MoxAgOgc7QAIHOlLv7CUQ/uFhj/v/zP+v/nfrU0maTW6GKYM3ZqzyoQJNuqHkR4/oS6mLG8AgI47t//+ybJvbH9ZeTBFFv//MoxAkMubrcyoHElOpgoANI/owub8ww1v+////+cWgwZ19JeurPehkQOcE3EdT0X3IoQVfP0PzjBfAAmD7LSZb9AHY7Vr/t//MoxBEMCbrQAILElDLSo2v5emsvLf/r/+n//Z2o////foZ1hRCPAX/9VgpVpLSqcWoIFRflVGv7Zah8BGp327fZOD52ir01//MoxBsL+JrAAKPYTNL4TgCrgUB9wHO6f////lXX//96VvsYA1BgbMcXI6L7ztSAag7Xe8fe04WaN3rdJTfHGeCCgdwoxv3N//MoxCYMgLq4AKPeTOveM/////4pdR//6/M8FwDMGW9OOWAnw41D6wN9TixKmSJPiDMgJt+wgQFY915IKCkiRZkNf/////sA//MoxC8M4KrRlJPSTI////6q8rgHMN+rxrNIEiLE/foTQYBfU6qdXeOltDUMdnKVq3JdqKhkWDDjbmMT//////2N///+VkCp//MoxDYM8KrRhHvSTAIAgD96+0nIGmhdmzAEML2+3XCLZma+iAha2NKIRUPSokBMm7CyIzIUPuZ/////+mWGroo5JI5AAIAA//MoxD0NMK7FlMPSTMpsBNAqjiMA8HkqP1mF23UF32nU1j55NYj5fIQ7MWXUgYWU2n/////8seHV/u78QM7drl2vNEIspPq5//MoxEMM2Kr2XmrYTnJ3fd4QQxav8p1PVjry5Ptcn44CaE0niatMTHAjizb//7P//+XVZjkkRkkgkAH1jMgZw8LZgIcpB1pW//MoxEoNELKoAM4eTEImcrQsBdZd7NBiSJh61LGA1Bq2J2oaxaZDfs9Z3///vJL/9CpFOPl5ZbLQNYrWonYvY2WJhO0YsjDV//MoxFAOSMbiXnpGcjjy6q1sf1VHJo/ZwK156OstqmtcxiLGgS2CQCKAENCIS+RqKrETepv/lkvPca86RFTD0u/+droVlJbL//MoxFETIQLKPnmMcgCtYrdfsSqymTVauE0MjA0P9ctQSbMSDtqLblnybh1ZFtW4YlW8USoeaNg0prHNZGjREAgWDqgOOrxh//MoxD8UUPqEXsDMcOrW4SipUWJG+GJYCiUJLi53+iqCUTkmBGQ0bZQAjA0JmCATAtKusIyoalSazIVzRr8k/pO/99DP57wa//MoxCgM8C50PjYSACwjdu4saoo+nI/+QjtLwOoMEG0CxChBQwZASwTcrEdF3q1c63p1T/YMFCgg5BYxgkGQkLCwuAmmhVv///MoxC8MkK4QAHvETMBC5mpMQU1FMy45OS41qqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqq" type="audio/mpeg" />
  Your browser does not support the audio element.
</audio>

## 什么是 WJ (Wrapped Joule)

就像汽油装在油桶里方便运输，J也通常会被装在智能合约中，这就是WJ (Wrapped Joule)。如果J是汽油，那么WJ就是桶装汽油。

WJ不能直接被当作燃料费使用。必须先unwrap（提取）把其中的J提取到web3地址上，然后才能使用这些提取出来的J用作燃料费。

提取方法是，打开Jouleverse区块链浏览器，搜索到你持有WJ的地址，点击WJ余额旁边的【unwrap】按钮，输入要提出的J数量，以及提取到的web3地址，点击【确认】。在弹出的Metamask确认页面中，检查各项参数正确后，点击确认，签名上链。等待10秒左右上链完成，即提取成功。

## 创世证明

Jouleverse在[创世区块<ExtLinkSvg />](https://jscan.jnsdao.com/#/block/0)中锚定了[比特币区块高度756208<ExtLinkSvg />](https://blockstream.info/block/0000000000000000000798c7481af9b174ef87d41c6e0fd0dc07d9971fb6513a)（时间戳记录为 2022-09-29 19:38:09 GMT +8 ）的哈希值，进行时间证明。创世区块时间戳为 1664451960，即 2022/9/29 GMT+8 19:46:00。

## 区块链浏览器

Jouleverse没有所谓的“官方”浏览器。以下是社群节点运行的“第三方”浏览器服务：

- 由[jnsdao](https://jnsdao.com)运行和维护的Jouleverse区块链浏览器：https://jscan.jnsdao.com
- 由[教链](https://xq.liujiaolian.com)运行和维护的Jouleverse区块链浏览器：https://jscan.liujiaolian.com

## 开始使用Jouleverse

要开始使用Jouleverse，只需三步走：1. 生成web3地址，创建钱包；2. 连接到Jouleverse网络；3. 获取Joule作为燃料费。

### 生成web3地址，创建钱包

Jouleverse使用与以太坊完全兼容的web3地址格式。形如：0x70a35Ba4e86d0788C1e2575fcA6D1aB482a5BF0E。

有两种方法可以生成你的web3地址：

1. 使用地址生成器 https://vanity-eth.tk/ 生成“keystore文件”和web3地址。参考[简明教程](https://github.com/hmisty/supernoobs/blob/main/materials/keystore_tut/README.md)。
2. 直接安装web3钱包App，在App中生成“助记词”和web3地址。参考[《小教程：安装MetaMask并添加Jouleverse区块链网络》](https://mp.weixin.qq.com/s/9TkupLVX1nqZlX4fz1TziA)。

市面上兼容以太坊的钱包App都可以。建议使用Metamask，又称小狐狸钱包。电脑建议安装chrome或firefox浏览器，到插件商店搜索metamask安装。苹果手机请切换海外苹果账号，然后到应用商店搜索metamask安装。安卓手机可以直接到[Metamask的官方github下载apk安装包](https://github.com/MetaMask/metamask-mobile/releases)。

如果是用第一种方法生成的keystore文件，需要在安装完Metamask后，通过导入keystore文件的方式把web3地址导入Metamask中显示和使用。

### 连接到Jouleverse网络

创建钱包并生成/导入了web3地址之后，还需要切换/连接到Jouleverse网络才能查看和管理该地址在Jouleverse的数字资产。需要两步：1. 添加RPC接入点；2. 切换网络。

添加Jouelverse网络的RPC有两个方法：
1. 电脑浏览器安装MetaMask插件后，或者在手机MetaMask App的内置浏览器中，打开Jouelverse区块链浏览器，点击首页的下方的深蓝色按钮【点此一键添加Jouleverse区块链主网】。
2. 或者，打开 [chainlist.org](https://chainlist.org/?search=jouleverse) ，搜索 jouleverse ，找到 Jouleverse Mainnet，点击“Connect Wallet”或“Add to MetaMask”一键添加。
3. 或者，手动配置：打开 设置 > 网络，点击【添加网络】> 手动添加一个网络，填写如下参数：，然后点击【保存】。
    - 网络名称(Network name): Jouleverse Mainnet
    - RPC (New RPC URL): https://rpc.jnsdao.com:8503
    - 链ID (Chain ID): 3666
    - 代币符号(Currency Symbol): J
    - 区块链浏览器地址(Block explorer URL): https://jscan.jnsdao.com

正确添加Jouleverse网络RPC之后，就可以点击Metamask左上角的网络切换，切换到刚刚添加的Jouleverse。

### 获取Joule作为燃料费

1. 冷启动。当你刚刚进入Jouleverse，此时你的web3地址上没有任何燃料(J)。你需要找一位持有WJ的人，提取一点儿J到你的web3地址即可。<br> 为了方便新人，Jouleverse建立了行星系统。你可以点开[“Jouleverse行星系统”](https://github.com/Jouleverse/planetary-system/blob/main/README.md)，添加任何一位星球的球长微信，加入TA管理的星球。完成[JTI可信身份认证](https://github.com/Jouleverse/jti2/blob/main/README.md)后，球长将会向你的web3地址免费赠送0.005 J新手燃料。
2. 地址上有J和WJ时。你可以自行unwrap WJ，提取少量J到自己的地址上，作为燃料费使用。（提醒：不要一次性提取过多J！提取J是不可逆的，一旦提取只能消耗不能移动）

## 通证经济模型

[Jouleverse的通证经济模型(tokenomics)](https://github.com/Jouleverse/genesis-treasury)非常简单：（宇宙大爆炸）创世总量1000亿J能量。线性释放，由[Timelock](https://github.com/Jouleverse/governance/blob/master/README.md)锁定。每月释放6000万J。分两个Timelock控制，1200万J用于核心空投，4800万J用于生态赞助。

其中，
- 核心空投部分采用独特的PoWh工作量证明机制实施“按劳分配”（按具有贡献的实际工作时间比例分配），为强制性空投，由“PoWh工作量委员会”负责按月统计和发放。[更多资料请查看“Jouleverse workspace”](https://github.com/Jouleverse/workspace/blob/main/README.md)。
- 生态赞助部分则通过[社区治理](https://github.com/Jouleverse/jips/blob/main/governance0.md)的方式，按照“每年每基金不超过12 x 1200万J、每期不超过2年”的原则拨款给社群发起、经治理投票批准成立的“生态基金”(ecofund)，由“生态基金”依据其工作规则，对Jouleverse的生态项目进行评定和给予WJ赞助。[参考Jouleverse首支生态基金](https://github.com/Jouleverse/jips/blob/main/jip-0005.md)。

## 核心治理会议CGC

Jouleverse的核心贡献者每周日下午14:00-15:30召开核心治理会议CGC，共同商议、推动和决策核心问题。会议为在线开放性会议，整个生态参与者都可以自由参会和参与讨论。[历次CGC会议纪要](https://github.com/Jouleverse/open-meetings)。

注意：CGC的决策范围是核心事务，即由每月1200万J、PoWh工作量证明机制所支持的工作。生态发展——即由每月4800万J支撑的项目——相关的话题，亦可以上会分享、讨论，但其决策权应归于[社区治理](https://github.com/Jouleverse/jips/blob/main/governance0.md)、JIPs、WJ质押投票等模块所组成的链上治理系统。

## JIPs

JIP是Jouleverse改进提案的缩写。任何社区成员都可以按照符合要求的格式，提交自己对Jouleverse如何改进的想法和提议。具体请参考[“JIPs的github”](https://github.com/Jouleverse/jips)。

## 节点网络

Jouleverse的节点网络由记账节点和见证节点组成。其中记账节点采用PoA (Proof-of-Authority)机制轮流记账。

审计节点由社区成员的节点自愿担任。审计节点每日会自动推送节点网络的最新审计信息到各节点运维者的邮箱，并同步[公示到github](https://github.com/Jouleverse/network-status/blob/main/daily-report.txt)。

## 成为核心贡献者，获取WJ空投

Jouleverse的基本原则是“按劳分配”。通过劳动贡献，可以赚取WJ。具体请参考[如何为Jouleverse做贡献并获得激励](https://how.jouleverse.com/#!incentive/how-to-contribute-to-jouleverse.md)。

当你参与到核心事务中时，你就可以登记为一个核心贡献者（需要通过高级KYC认证）。

核心贡献者分配每月释放的1200万J。分配规则是PoWh工作量证明。

---

最简单的，可以先从搭建一个Jouleverse见证节点并入网开始，加入核心贡献者行列。具体参考：[Jouleverse主网节点搭建指南](https://how.jouleverse.com/#!network/how-to-setup-jouleverse-node.md)。

还有哪些其他核心事务/工作需要大家的积极参与和贡献呢？可以参考[workspace specs](https://github.com/Jouleverse/workspace/blob/main/work-package-specs.mediawiki)。

## 开发生态项目，申请WJ赞助

### 在Jouleverse上进行web3开发

Jouleverse是和以太坊高度兼容的，所以，可以直接参考绝大部分有关以太坊web3开发的资料。比如，AA的[《精通以太坊》](https://github.com/inoutcode/ethereum_book)。

常用的web3开发库：
- 前端页面/nodejs 可以用 [web3.js](https://web3js.readthedocs.io/)
- python 可以用 [web3.py](https://web3py.readthedocs.io/)
- php 可以用 [web3.php](https://github.com/web3p/web3.php)
- java 可以用 [web3j](https://docs.web3j.io/4.11.0/)

等等。

### 申请赞助

生态基金每一支都有其单独的赞助规则。先参考一下[首支生态基金的相关信息](https://github.com/Jouleverse/ecofund1)吧。


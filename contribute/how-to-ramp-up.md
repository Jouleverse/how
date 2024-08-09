# Jouleverse(焦耳宇宙)漫游指南

Author | 教链([evan.j](https://jscan.jnsdao.com/#/jns/evan.j)), XXX
-|-
Reviewer | -

## Jouleverse释义

Jouleverse 一词由国际公制能量单位 Joule(焦耳) 和 universe(宇宙) 的后缀 -verse 拼合而成。含义是焦耳宇宙或者能量宇宙。

狭义的 Jouleverse 是一个完全由社群驱动的、去中心化的、面向合规的、不发币的开放区块链。愿景是成为一个合规的web3基础设施，支持大量web3应用的繁荣生态。

广义的 Jouleverse 是一个包含链节点、大量web3应用、活跃的社群和用户(参阅下文“行星系统”)的完整的web3元宇宙。

## Joule

Joule (J) 是国际公制能量单位，也是Jouleverse的使用费——或者叫做燃料费（gas fee）——的计量单位。

要使用Jouleverse，就要消耗燃料（能量），就像使用云计算需要消耗资源费，开汽车需要消耗汽油一样。

Jouleverse高度兼容以太坊。其燃料费计算公式亦与后者相同：gas fee (J) = gas limit (unit) * gas price (gwei/unit) * 1/10^9.

Joule的发音是“焦耳”，点击听美式发音示范：

<audio controls>
  <source src="data:audio/mpeg;base64,//MoxAAJgFIUAUMQANAAASgYuAYGBvAgAIoAAHP/8EBoIDQff/yn//hgo7+rw//+UdwfegQ6EiWQ/2/X/z7H//n//5O8nf////MoxBUR0xqMAYJQAZOfH58f///nx+P3EWP3EX///+Lbg3g3k4AsQ5gBMfCwDX////+cSA1kRILZQkFtDBbCFf//f/////////MoxAgO+yLQAYEoAP//////+RvpZ3a+kzuahbI6DjTTuii6gICBQqUwW9+/+UXeQURiFHlF2jijRooGlVrHHiD/y/////////MoxAcO2r7gAcEoAf///////+vYh11c9bn1dkVBQw4XVgEE4dOITlOqGF1sZFopjuQgo4hQaZ3FDRne6Mw7+p+VAtoAtbbo//MoxAYNSjMl/hAEmv3CCCNun//qu7s+QqIRjqZqVRehKVq59GT0T8iqRkMQSYiLva5OjUFHJTu+24DUKv6OZX1qOJhXAPB0//MoxAsPaXLkymiElPJOWlG/0EW////7///7vMYyKFGOX0JFxYGgVMiMKPrdxFBkWCgdewXDVVqF8rur7cRRFf2Pk8IyBLSO//MoxAgOgc7QAIHOlLv7CUQ/uFhj/v/zP+v/nfrU0maTW6GKYM3ZqzyoQJNuqHkR4/oS6mLG8AgI47t//+ybJvbH9ZeTBFFv//MoxAkMubrcyoHElOpgoANI/owub8ww1v+////+cWgwZ19JeurPehkQOcE3EdT0X3IoQVfP0PzjBfAAmD7LSZb9AHY7Vr/t//MoxBEMCbrQAILElDLSo2v5emsvLf/r/+n//Z2o////foZ1hRCPAX/9VgpVpLSqcWoIFRflVGv7Zah8BGp327fZOD52ir01//MoxBsL+JrAAKPYTNL4TgCrgUB9wHO6f////lXX//96VvsYA1BgbMcXI6L7ztSAag7Xe8fe04WaN3rdJTfHGeCCgdwoxv3N//MoxCYMgLq4AKPeTOveM/////4pdR//6/M8FwDMGW9OOWAnw41D6wN9TixKmSJPiDMgJt+wgQFY915IKCkiRZkNf/////sA//MoxC8M4KrRlJPSTI////6q8rgHMN+rxrNIEiLE/foTQYBfU6qdXeOltDUMdnKVq3JdqKhkWDDjbmMT//////2N///+VkCp//MoxDYM8KrRhHvSTAIAgD96+0nIGmhdmzAEML2+3XCLZma+iAha2NKIRUPSokBMm7CyIzIUPuZ/////+mWGroo5JI5AAIAA//MoxD0NMK7FlMPSTMpsBNAqjiMA8HkqP1mF23UF32nU1j55NYj5fIQ7MWXUgYWU2n/////8seHV/u78QM7drl2vNEIspPq5//MoxEMM2Kr2XmrYTnJ3fd4QQxav8p1PVjry5Ptcn44CaE0niatMTHAjizb//7P//+XVZjkkRkkgkAH1jMgZw8LZgIcpB1pW//MoxEoNELKoAM4eTEImcrQsBdZd7NBiSJh61LGA1Bq2J2oaxaZDfs9Z3///vJL/9CpFOPl5ZbLQNYrWonYvY2WJhO0YsjDV//MoxFAOSMbiXnpGcjjy6q1sf1VHJo/ZwK156OstqmtcxiLGgS2CQCKAENCIS+RqKrETepv/lkvPca86RFTD0u/+droVlJbL//MoxFETIQLKPnmMcgCtYrdfsSqymTVauE0MjA0P9ctQSbMSDtqLblnybh1ZFtW4YlW8USoeaNg0prHNZGjREAgWDqgOOrxh//MoxD8UUPqEXsDMcOrW4SipUWJG+GJYCiUJLi53+iqCUTkmBGQ0bZQAjA0JmCATAtKusIyoalSazIVzRr8k/pO/99DP57wa//MoxCgM8C50PjYSACwjdu4saoo+nI/+QjtLwOoMEG0CxChBQwZASwTcrEdF3q1c63p1T/YMFCgg5BYxgkGQkLCwuAmmhVv///MoxC8MkK4QAHvETMBC5mpMQU1FMy45OS41qqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqqq" type="audio/mpeg" />
  Your browser does not support the audio element.
</audio>

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

1. 使用地址生成器 https://vanity-eth.tk/ 生成“keystore文件”和web3地址。参考刘教链超级小白课的[简明教程](https://github.com/hmisty/supernoobs/blob/main/materials/keystore_tut/README.md)。
2. 直接安装web3钱包App，在App中生成“助记词”和web3地址。(TODO: 教程)

市面上兼容以太坊的钱包App都可以。建议使用Metamask，又称小狐狸钱包。电脑建议安装chrome或firefox浏览器，到插件商店搜索metamask安装。苹果手机请切换海外苹果账号，然后到应用商店搜索metamask安装。安卓手机可以直接到Metamask的官方github下载安装包 —— [v7.27.0 apk链接](https://github.com/MetaMask/metamask-mobile/releases/download/v7.27.0/app-prod-release.apk)。

如果是用第一种方法生成的keystore文件，需要在安装完Metamask后，通过导入keystore文件的方式把web3地址导入Metamask中显示和使用。

### 连接到Jouleverse网络

创建钱包并生成/导入了web3地址之后，还需要切换/连接到Jouleverse网络才能查看和管理该地址在Jouleverse的数字资产。需要两步：1. 添加RPC接口；2. 切换网络。

添加Jouelverse网络的RPC有两个方法：
1. 如果是插件版Metamask，直接在浏览器打开Jouelverse区块链浏览器，点击首页的下方的深蓝色按钮【点此一键添加Jouleverse区块链主网】。
2. 手动添加：打开 设置 > 网络，点击【添加网络】> 手动添加一个网络，填写如下参数：，然后点击【保存】。
    - 网络名称(Network name): Jouleverse
    - RPC (New RPC URL): https://rpc.jnsdao.com:8503
    - 链ID (Chain ID): 3666
    - 代币符号(Currency Symbol): J
    - 区块链浏览器地址(Block explorer URL): https://jscan.jnsdao.com

正确添加Jouleverse网络RPC之后，就可以点击Metamask左上角的网络切换，切换到刚刚添加的Jouleverse。

### 获取Joule作为燃料费



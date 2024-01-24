# Jouleverse Mainnet 节点搭建指南

版本：

* 1.9 evan.j: 2024.1.24 增加对于重做数据的警告，以及更多指引
* 1.8 evan.j: 2024.1.19 迁移到Jouleverse知识库
* 1.7 evan.j: 2024.1.17 修正防火墙端口号。误将测试网端口号合并进来了。感谢 @老谢 指出错误。
* 1.6 evan.j: 2024.1.17 补充升级节点停止docker的前置操作。增加节点包镜像。增加入网一章节，包括添加审计节点，以及检查节点包版本号等
* 1.5 evan.j: 2024.1.15 节点包升级为rc 20240115 - 增补了11个记账节点、7个bootnode-witness节点；补全了一些操作，不需要再交叉查看测试网教程
* 1.4 evan.j: 2024.1.3 节点包改用最新的rc 20240103; 登记表增加转入质押WJ的交易hash; 修改入网、退网流程
* 1.3 evan.j: 2023.10.24 简化节点运行步骤；添加备份nodekey的方法
* 1.2 evan.j 2023.10.7 use rc 20231007
* 1.1 evan.j 2023.10.4 fix ports
* 1.0 evan.j 2023.9.29

号外：节点 @老谢 自制两份保姆级教程，一份是见证节点搭建的，一份是见证节点升级的，可在节点群中联系索取。

## PoWh激励标准

主网记账节点或见证节点要求独立主机、独立IP运行，每节点每月计5h算力。

## 简明步骤

1. 准备keystore账户，用户签名出块
2. 准备独立云主机、独立IP，最低配置（2核4G内存40G硬盘），Ubuntu 20.04 Linux带docker，防火墙打开30311/tcp和30311/udp （见证节点请再打开8501/tcp）【注意与testnet端口号皆有不同】
3. 下载节点软件包 jouleverse-node-20240115.tar.gz ，并启动节点
4. 在节点群里通知其他节点投票，批准自己节点入网
5. 入网后，填写主网节点信息采集表

## 账户准备

keystore是一种把私钥加密保存在文本文件中的技术。keystore文件是加密保存了私钥的文本文件（json格式）。可以用 https://vanity-eth.tk/ 这个工具生成。记住keystore对应的地址0xAAA...（下文称为“签块地址”），并把keystore文件下载到电脑上，重命名为mainnet.keystore 。请妥善保管keystore文件并记住其解锁密码。稍后需要将该文件放到云主机上面去。

《教程：使用Vanity-ETH地址生成器创建keystore账户》：https://mp.weixin.qq.com/s/MUBWPodZ8V3_qqOcSTs8Aw

注意：不要混用测试网的keystore。

## 购买云主机

配置最低2核4G内存40G硬盘。系统镜像选用Ubuntu 20.04 LTS + Docker的版本。

要求：全新主机，独立IP地址。主网记账节点云主机请确保至少1年或以上有效期，以持续稳定运行。

### 配置云主机防火墙

在云主机管理后台，找到防火墙配置，关闭所有非必要的端口，打开30311/tcp（即：端口号 30311 协议 tcp）和30311/udp（端口号 30311 协议 udp），分别用于节点数据传输和节点组网信令交换。

另外，见证节点请打开8501/tcp（用于响应rpc请求）和ICMP（用于响应ping）。目前非必需。

## 准备工作

从云主机管理后台登陆云主机终端，从github repo下载rc 20240115版本的软件包：
```
wget https://github.com/Jouleverse/jouleverse-node/archive/refs/tags/jouleverse-node-20240115.tar.gz
```

注：如果无法下载，可换用镜像：```wget http://bootnode.jnsdao.com/mirror/jouleverse-node-20240115.tar.gz```

检查shasum： ``` shasum jouleverse-node-20240115.tar.gz ``` 
结果应该是 
```
b3e551b40d39f71f8ac0ca2b44bdfb0a320d2ca5  jouleverse-node-20240115.tar.gz
```
这证明软件包未损坏或被篡改。

解压缩：```tar xvfz jouleverse-node-20240115.tar.gz```

解压缩出来的目录名称需要改一下：```mv jouleverse-node-jouleverse-node-20240115 jouleverse-node-20240115```

拉docker镜像（如果拉过就不需要了）：```sudo docker pull ubuntu:20.04```

## 初始化数据目录

Note: **警告：如果只是重启/升级节点而不是第一次搭建，请不要重新初始化数据目录！否则可能会造成节点信息变化，审计报错！**

如果是第一次搭建和运行节点：

> 创建目录（若创建过就不需要了）：```mkdir ~/data```

> 初始化mainnet数据目录：
```
sudo docker run -v ~/jouleverse-node-20240115:/j -v ~/data:/data -it ubuntu:20.04 /j/geth init --datadir /data/mainnet /j/genesis-mainnet.json
```

---

Note: **再次警告：如果只是重启节点/升级节点而不是第一次搭建，请不要重做节点数据！否则可能会造成节点信息变化，审计报错！**

如果是重做节点数据，重新运行节点，但是希望保持节点id和enode不变（方法关键在于```备份nodekey```）：

> 备份nodekey：```sudo cp ~/data/mainnet/geth/nodekey ~/data/nodekey-20240119.bak```（请把20240119改为你操作的日期；如果你在当日进行了多次操作，请把次数加在bak后面，比如 nodekey-20240119.bak2 nodekey-20240119.bak3 等等，下同）

> 查看一下备份的nodekey：```sudo cat ~/data/nodekey-20240119.bak && echo``` 内容应该是一个十六进制字符串（没有开头的0x）【nodekey属于机密内容！不要截屏！不要截屏！不要截屏！】

> 删除节点数据：```sudo mv ~/data/mainnet ~/data/mainnet-20240119.old``` （请把20240119改为你操作的日期；如果你在当日进行了多次操作，请把次数加在old后面，比如 mainnet-20240119.old2 mainnet-20240119.old3 等等）

> 重新初始化mainnet数据目录：命令见上面

> 把刚刚备份的nodekey文件拷贝到新的mainnet目录里：```sudo cp ~/data/nodekey-20240119.bak ~/data/mainnet/geth/nodekey```

---

Note: **注意：见证节点可跳过这一节**

如果要启动记账节点，则还需要创建mainnet.keystore和password-mainnet.txt两个文件：（见证节点不需要）

把主网签块账户keystore内容贴到主机上 ~/data/mainnet.keystore ，并创建密码文件 ~/data/password-mainnet.txt 。

keystore文件粘贴和创建方法： ``` cat > ~/data/mainnet.keystore ``` 粘贴主网keystore内容，按Ctrl+D，保存退出。

创建好之后用```cat ~/data/mainnet.keystore```命令检查一下内容正确无误。

内容应该类似这样：
```
{"address":"0x38885d668d422e07b1d3b205f021b2d4363051e9","crypto":{"kdf":"pbkdf2","kdfparams":{"c":262144,"dklen":32,"prf":"hmac-sha256","salt":"6a2017.......41d4e5aa516f706a"},"cipher":"aes-128-ctr","ciphertext":"12b662d.....e332","cipherparams":{"iv":"a29fb2....6d4f95769822"},"mac":"85e521....63f8d0b"},"id":"a30fe...-....-....-....-....bc57cbe2e","version":3}
```

同样方法再创建一个密码文件： ``` cat > ~/data/password-mainnet.txt ``` 输入你的keystore文件的解锁密码，Ctrl+D保存退出。

创建好之后用```cat ~/data/password-mainnet.txt```检查一下内容正确无误。

把keystore文件拷贝到正确位置：```sudo cp ~/data/mainnet.keystore ~/data/mainnet/keystore/```

---

以上步骤都正确完成后的目录结构如下：

```
~ （当前账户的家目录）
|
|- jouleverse-node-20240115/ 主网节点软件包（含配置文件）
|- data/ 数据目录
    |- 【仅记账节点】mainnet.keystore 签块账户keystore文件（备份）
    |- 【仅记账节点】password-mainnet.txt 签块账户keystore解锁密码
    |- mainnet/ 区块链数据（主网）
        |- geth/... 数据库文件...
        |- keystore/ 签块账户keystore文件保存目录
            |- 【仅记账节点】mainnnet.keystore 签块账户keystore文件（主网）
```

---

Note: **注意：下面，根据你是要搭建见证节点还是记账节点，在“选项一”和“选项二”两个里面选一个即可！**

## 选项一：启动见证节点

Note: **注意：如果是重启节点/升级节点，那么要先执行命令，停止节点的运行：```sudo docker stop jouleverse-mainnet```**
然后一条命令清除所有已停止的容器（当遇到提示容器已存在错误时可随时执行）：```sudo docker container prune```

启动见证节点。执行下述命令，后台运行节点（关闭远程终端后会持续运行）：
```
sudo docker run -v ~/jouleverse-node-20240115:/j -v ~/data:/data --name "jouleverse-mainnet" -p 30311:30311/tcp -p 30311:30311/udp -p 8501:8501 -d ubuntu:20.04 /j/geth --config /j/node-mainnet-witness.toml --snapshot=false --ignore-legacy-receipts 
```

确认节点成功运行：```sudo docker ps```

检查后台运行节点的日志：```sudo docker logs -n 100 -f jouleverse-mainnet```

观察节点运行日志，应该能够找到其他节点并开始同步区块链，出现类似这样的日志：
```
INFO [09-28|12:52:39.426] Imported new chain segment               blocks=2048 txs=2 mgas=0.042 elapsed=3.446s      mgasps=0.012 number=37943 hash=a43ebf..37a8c0 age=11mo3w42m dirty=2.69KiB
INFO [09-28|12:52:43.182] Imported new chain segment               blocks=2048 txs=13 mgas=0.273 elapsed=3.732s      mgasps=0.073 number=39991 hash=110c48..f0999f age=11mo2w6d  dirty=2.69KiB
INFO [09-28|12:52:46.944] Imported new chain segment               blocks=2048 txs=3  mgas=0.063 elapsed=3.747s      mgasps=0.017 number=42039 hash=1a0a88..98d165 age=11mo2w6d  dirty=2.69KiB
INFO [09-28|12:52:50.256] Imported new chain segment               blocks=2048 txs=1  mgas=0.021 elapsed=3.291s      mgasps=0.006 number=44087 hash=3ed781..448020 age=11mo2w5d  dirty=2.69KiB
```

日志不断产生，持续同步区块，则说明节点正常运行了！（随时按 Ctrl + C 退出查看日志 —— 不会中止节点运行）

待半小时到一小时后，区块链同步完成，追上最新区块高度。查看运行日志，并截图【节点运行日志截图】。

## 选项二：启动记账节点

Note: **注意：如果是重启节点/升级节点，那么要先执行命令，停止节点的运行：```sudo docker stop jouleverse-mainnet```**
然后一条命令清除所有已停止的容器（当遇到提示容器已存在错误时可随时执行）：```sudo docker container prune```

启动记账节点，以下述命令后台运行节点（关闭远程终端后会持续运行）：
``` 
sudo docker run -v ~/jouleverse-node-20240115:/j -v ~/data:/data --name "jouleverse-mainnet" -p 30311:30311/tcp -p 30311:30311/udp -d ubuntu:20.04 /j/geth --config /j/node-mainnet-miner.toml --snapshot=false --ignore-legacy-receipts --unlock '0xddbe0d8374c6180e1a62249ad5caa7e4b64c0f4c' --password /data/password-mainnet.txt --mine 
```

<small>**注：请将 0xddbe0d8374c6180e1a62249ad5caa7e4b64c0f4c 替换为你自己的mainnet.keystore主网签块账户地址。**</small>

确认节点成功运行：```sudo docker ps```

检查后台运行节点的日志（需要时使用）：```sudo docker logs -n 100 -f jouleverse-mainnet```

观察节点运行日志，应该能够找到其他节点并开始同步区块链（日志同上），同时，还应该能看到尝试出块和“未授权的签块者”错误信息，类似：
```
WARN [09-28|12:52:18.033] Block sealing failed                     err="unauthorized signer"
```

日志不断产生，持续同步区块，则说明节点正常运行了！（随时按 Ctrl + C 退出查看日志 —— 不会中止节点运行）

待半小时到一小时后，区块链同步完成，追上最新区块高度。查看运行日志，并截图【节点运行日志截图】。

## 审计和入网

接下来还要建立一下到审计节点（自2024.1.16起由节点 @Jeff 进行审计）的连接：

进入后台运行节点的geth console控制台（需要时使用）：
```
sudo docker exec -it jouleverse-mainnet /j/geth attach /data/mainnet/geth.ipc
```

在geth console执行下述命令：
```
admin.addPeer('enode://f3e4e524d89b4cdb9ee390d9485cee4d6a5e9a260f5673cab118505cc3e69fe8365bc00434222d27fe4082ca798b13ad8e7e139d1315f635fd0e46dbe96fa809@bootnode-jeff.jnsdao.com:30311')
```

添加后，稍等片刻，执行下述命令，确认已经和审计节点建立了连接：
```
admin.peers.filter(n => n.id == '36d1c18a197fea99e9b55b111b03ab03866367838b3017ae91984e0648e3f677')
``` 

应该能够看到正确的审计节点的连接信息，类似于：
```
[{
    caps: ["eth/66", "eth/67"],
    enode: "enode://f3e4e524d89b4cdb9ee390d9485cee4d6a5e9a260f5673cab118505cc3e69fe8365bc00434222d27fe4082ca798b13ad8e7e139d1315f635fd0e46dbe96fa809@43.136.53.164:30311",
    id: "36d1c18a197fea99e9b55b111b03ab03866367838b3017ae91984e0648e3f677",
    name: "Geth/v1.11.3-jouleverse-5d8dcb81-20230926/linux-amd64/go1.16.2",
    network: {
      inbound: false,
      localAddress: "172.17.0.2:35036",
      remoteAddress: "43.136.53.164:30311",
      static: true,
      trusted: false
    },
    protocols: {
      eth: {
        difficulty: 5379019,
        head: "0x702d6211fc6a2a277fbc16a3890f5881bb5bc6ef145867e535cbeacc61febcb3",
        version: 67
      }
    }
}]
```
把该命令的执行结果截图【审计节点连接截图】。

...

最后，确认一下当前docker运行的节点包版本：

在Linux命令提示符下，执行命令：```sudo docker inspect jouleverse-mainnet | grep -i source```

应该看到类似如下结果：
```
        "Source": "/home/evan/jouleverse-node-20240115",
        "Source": "/home/evan/data",
```

截图【节点包版本截图】。

### 见证节点入网流程：

1. 搭建节点并运行，查看日志，等待半小时到一小时，区块同步到最新高度
2. 将上面的三张截图【节点运行日志截图】【审计节点连接截图】【节点包版本截图】，发到节点预备群，请大家帮忙审查，确认运行无误后，填写节点信息登记表：https://docs.qq.com/form/page/DTEp2cEdsa0lTelB0
3. 填表完成后，在节点预备群提请审计节点将你的见证节点加入审计列表
4. 审计通过后，申请加入jouleverse core（核心贡献者组）

恭喜成功入网！

### 记账节点入网和退网流程【必读】：

1. 搭建节点并运行，查看日志，等待半小时到一小时，区块同步到最新高度
2. 将上面三张截图【节点运行日志截图】【审计节点连接截图】【节点包版本截图】，发到节点预备群，请大家帮忙审查，确认运行无误
3. 向节点PoS质押合约（0xDb11694Ed05Db4a6230BDFd0914094FE7CE73646 ）转入100万WJ，并记录下转账的tx hash
4. 填写节点信息登记表：https://docs.qq.com/form/page/DTEp2cEdsa0lTelB0
5. 填表完成后，在节点预备群提请审计节点将你的记账预备节点（miner*）加入审计列表
6. 审计通过后，在节点预备群发出你的节点信息（IP, 签块地址），请其他记账节点审议和投票
7. 投票通过后，检查新“三件套”（1- 节点运行日志截图，即docker logs jouleverse-mainnet；2- geth控制台的clique.status()；3- geth控制台的clique.getSnapshot() ），并一一截图发到节点预备群，请大家帮助审查，确认出块无误
8. 确认正常记账后，请审计节点把你节点从预备记账（miner*）变更为正式记账（miner）
9. 一切完成后，申请加入jouleverse core（核心贡献者组）

恭喜成功入网！

...

退网流程：

请其他节点投票移除自己的节点 -> 检查出块情况，确认自己节点已不在网络中-> 请审计节点将自己节点移除出审计列表 -> 请PoS多签钱包管理人退回质押的100万WJ -> 关闭节点 -> 成功退网

### 附：clique投票方法

#### 投票批准其他节点接入网络

节点控制台执行：

```
> clique.propose('替换为待批准节点的签块地址0x...', true)
```

撤销批准（反悔）：
```
> clique.discard('替换为待批准节点的签块地址0x...')
```

#### 投票踢掉网络中的签块节点

节点控制台执行：

```
> clique.propose('替换为待批准节点的签块地址0x...', false)
```

撤销踢人（反悔）：
```
> clique.discard('替换为待批准节点的签块地址0x...')
```


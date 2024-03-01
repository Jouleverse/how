# 如何找回nodekey文件

Author | cijin([news.j](https://jscan.jnsdao.com/#/jns/news.j))
-|-
Reviewer | 教链

> 说明：本文档适用于机器上有备份与云文档登记或节点信息一致信息的nodekey文件，但当前运行nodekey与云文档不相符的情况。思路是找到与当前节点nodekey不同的文件进行替换，然后重启节点，尝试恢复节点信息与云文档登记的一致

Note: 注意：nodekey是类似私钥的机密文件。cat是查看命令，cat nodekey的内容时，显示的内容一定要保密。不要截屏！不要截屏！不要截屏！

```
# 0. 先确认一下当前节点信息与登记审计的不相符合（id和enode信息均不匹配），确认一下当前nodekey错误
sudo docker exec -it jouleverse-mainnet /j/geth attach --exec 'admin.nodeInfo' /data/mainnet/geth.ipc

# 如果结果中的enode和id信息与登记审计信息一致，说明nodekey正确，不必进行修复！

# 1. 查找本机是否存在备份过的nodekey文件（由于节点教程数据目录都在/home下所以只查找/home，加快速度）
sudo find /home -name nodekey

# 可以看到类似这样的结果：
/home/lighthouse/data/mainnet.bak-till-2064563/geth/nodekey
/home/lighthouse/data/mainnet.bak-till-2377848/geth/nodekey
/home/lighthouse/data/mainnet/geth/nodekey
/home/lighthouse/data/mainnet.bak-till-2633273/geth/nodekey
/home/lighthouse/data/mainnet.old20240214/geth/nodekey
/home/lighthouse/data/mainnet.bak-till-2833183/geth/nodekey

# 2. 把备份目录中的nodekey文件逐一替换到节点数据目录，进行尝试【警告：该指令会覆盖掉当前节点数据目录中的nodekey文件且不可恢复！】
sudo cp /home/lighthouse/data/mainnet.bak-till-2064563/geth/nodekey /home/lighthouse/data/mainnet/geth/nodekey

# 3. 重启节点
sudo docker restart jouleverse-mainnet

# 4. 跳到第0步，检查替换nodekey并重启节点后，节点的enode和id信息是否与登记审计的信息一致？
#    对第1步找到的nodekey文件逐一进行尝试，直至发现正确的nodekey文件即可。
```

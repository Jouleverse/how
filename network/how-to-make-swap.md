# 如何创建虚拟内存(Swap)  

> 增加虚拟内存（swap），用于解决内存不足，间接导致docker退出的问题

1、节点运行一点时间后，`geth` 内存占用会变高，会导致`kswapd0`来主动分配虚拟内存，来应对内存不足的问题

2、实际操作下来，`kswapd0`自己会把CPU跑满，导致docker被系统退出

3、解决方案：主动设置虚拟缓存（swap），避免`kswapd0`来临时创建、释放等操作，从而避免CPU过载。

4、设置虚拟内存（swap）流程

```
# free -m 查看一下是否设置过 Swap
free -m
-----------------------------------------------------------------------------------
               total        used        free      shared  buff/cache   available
Mem:            1963        1741          95           1         126          80
Swap:          4383         666       3717
-----------------------------------------------------------------------------------
# 如果已经创建`Swap`，下面的命令不需要再次执行


# 1. 创建 4G Swap 文件（一般设置为物理内存的2倍）
sudo fallocate -l 4G /swapGeth

# 2. 查看是否创建成功
ls -lh /swapGeth

# 3. 按照网络上的资料，设置一下权限会更安全一些
sudo chmod 600 /swapGeth

# 4. 将 `/swapGeth` 作为 Swap
sudo mkswap /swapGeth

# 5. 在 `/etc/fstab` 文件中，增加配置，用于让系统重启后，也可以继续生效
sudo sh -c 'echo "/swapGeth swap swap sw 0 0" >> /etc/fstab'


# 6. 验证`/etc/fstab`中，结尾是否包含了 `/swapGeth swap swap sw 0 0`
tail /etc/fstab

# 7. 启用Swap
sudo swapon /swapGeth

```


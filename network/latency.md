# 2.2 了解各类延迟指标

既然本章的主题是构建足够快的网络服务，那么我们就需要对“快”有个基本了解。

伯克利大学有个动态网页[^注1]可以查看每年计算机中各类操作耗时、延迟的变化。我汇总了 2020 年的数据供读者参考，了解这些延迟指标有助于设计和比较不同的解决方案以及评估服务质量。

<center><p>表2-1 计算机中各类延迟数据</p></center>

操作|延迟
:---|:--:|
L1 缓存查询| 1 ns
分支预测错误（Branch mispredict）| 3 ns
L2 缓存查询 | 4 ns
互斥锁/解锁 | 17 ns
在 1Gbps 的网络上发送 2KB | 44 ns
主存访问 | 100 ns
Zippy 压缩 1KB | 2,000 ns ≈ 2 μs
从内存顺序读取 1 MB | 3,000 ns ≈ 3 μs
SSD 随机读 | 16,000 ns  ≈ 16 μs
从 SSD 顺序读取 1 MB | 49,000 ns  ≈ 49 μs
同一个数据中心往返 | 500,000 ns  ≈ 0.5 ms
从磁盘顺序读取 1 MB | 825,000 ns  ≈ 0.8 ms
磁盘寻址 | 2,000,000 ns ≈ 2 ms
从美国发送到欧洲的数据包 | 150,000,000 ns ≈ 150 ms

<div  align="center">
	<img src="../assets/time.png" width = "300"  align=center />
	<p>图 2-2 秒(s)、毫秒(ms)、微秒 (μs)、纳秒(ns)之间关系 </p>
</div>


> 注1: https://colin-scott.github.io/personal_website/research/interactive_latency.html
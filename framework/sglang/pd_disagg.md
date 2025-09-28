# 1. design
## 1.1 动态PD连接 Dynamic Connection
为每个请求建立一堆p和d的服务连接，方便动态扩缩容。
## 1.2 非阻塞传输 Non-blocking transfer
发送和接受是非阻塞的，在后台线程中进行。
## 1.3 异构并行 Heterogeneous Parallelism
P和D支持不同的TP size。
## 1.4 基于RDMA传输
使用RDMA中的QP queue pairs建立连接。

# 2. PD负载均衡 Load balancing
## 2.1 最小负责策略
当请求到达时，选择负载最小的一对pd连接。
## 2.2 自动扩缩容
根据p d worker的利用率，根据实际使用情况添加或者移除这些worker。

# 3. Event Loop
在原有的SGLang调度事件循环之上，添加了非阻塞的发送者和接收者操作。

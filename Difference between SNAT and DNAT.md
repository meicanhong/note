1. 源网络地址转换（SNAT）：
顾名思义，SNAT 是一种在从私有 IP 地址连接到公共 IP 地址时通常将源 IP 地址转换的技术。它将请求中的源客户端 IP 地址映射到 BIG-IP 设备上定义的转换。当内部主机需要向外部主机或公共主机发起会话时，这是最常见的 NAT 形式。
2. 目标网络地址转换（DNAT）：
DNAT，顾名思义，是一种在从公共 IP 地址连接到私有 IP 地址时通常转换目标 IP 地址的技术。它通常用于将发往特定 IP 地址或 IP 地址上特定端口的数据包重定向到一台主机上的不同地址，主要是在不同主机上。

3. SNAT 和 DNAT 的区别：

| **SNAT** | **DNAT** |
| --- | --- |
| 它通常用于将私有地址或端口更改为公共地址或端口，以便数据包离开网络。 | 它通常用于将目标为公共地址或端口的传入数据包重定向到网络内部的私有 IP 地址或端口。 |
| 它将连接中的源 IP 地址转换为定义的 BIG-IP 系统 IP 地址。 | 它将受设备保护的内部服务器的 IP 地址转换为公共 IP 地址。  |
| 它用于更改数据包的源地址。   | 它用于更改数据包的目标地址。   |
| 它还会更改 TCP/UDP 标头中的源端口。   | 它还会更改 TCP/UDP 标头中的目标端口。   |
| 它通常允许内部的多个主机获取外部的任何主机。  | 它通常允许外部的多个主机在内部获取单个主机。   |
| 它在做出路由决定之后执行。   | 它在做出路由决策之前执行。   |
| 在此，目标 IP 地址保持不变，源 IP 地址发生变化。   | 在此，源 IP 地址保持不变，目标 IP 地址发生变化。  |
| 局域网内和防火墙后面的客户端需要浏览 Internet。 | 网站托管在防火墙后面的数据中心内，需要用户通过 Internet 访问 |


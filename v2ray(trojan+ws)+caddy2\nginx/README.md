介绍：

此配置为v2ray新增trojan协议，以ws方式传输，实现了兼容trojan-go的ws模式，即直接使用trojan-go客户端连接。

另外通过 caddy2 或 nginx 前置 v2ray server 实现 ws 反向代理，tls 由 caddy2 或 nginx 提供及处理。

原理图： trojan-go client <------ ws+tls ------> caddy2\nginx <- ws -> v2ray server

注意：若系统版本过低，其对应发行版仓库自带 nginx 预编译程序包可能不支持 tls1.3；如需要支持 tls1.3，必须先升级 OpenSSl 版本大于 1.1.1，再进行 nginx 源代码编译和安装。

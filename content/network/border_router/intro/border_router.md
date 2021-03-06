---
title: "边界路由器"
date: 2020-12-01T00:38:25+09:00
draft: false
weight: 1
---

边界路由器是用于连接不同网络的路由器，青云的边界路由器可以连接多种不同的网络场景：第一种，可以连接不同 VPC 内部的虚拟私有网络；第二种，可以连接虚拟私有网络和物理网络；第三种，可以连接 VPC 与专线或者 SD-WAN。

场景一：连接不同 VPC 内部的虚拟私有网络，实现更大规模的主机组网，和更高的网络性能。此前最常用的方式是通过隧道来打通不同的VPC，边界路由器可以避免隧道带来的种种弊端，比如隧道必须消耗公网流量费用，带宽受限等等。

场景二：连接虚拟私有网络和物理网络，实现虚拟机和物理机混合组网，例如 Oracle 数据库或者 SAP 更希望在 BM 主机中运行，与 Web Server所在的虚拟主机混合组网。

场景三：连接虚拟私有网络和 SD-WAN，实现青云公有云与用户私有部署环境的直联，服务之间的调用与纯内网访问完全一致，仿佛用户有了一套企业专用的网络。



如下图所示, 客户端 1 在私有网络 192.168.128.0/24 中, 客户端 2 在私有网络 172.17.0.0/24 中, 客户端 3 在私有网络 192.168.130.0/24 中。
通过以下步骤即可实现客户端 1 与客户端 2 , 3 互联。

1. 创建边界路由器。

2. 关联边界路由器: 将客户端 1 和客户端 2 所在的私有网络关联到边界路由器, 将客户端 3 所在的VPC关联到边界路由器。

3. 配置边界路由器策略: 为客户端 1 , 2 , 3 所在的私有网络添加边界路由器策略。

![](/network/border_router/_images/intranet_router_topology.jpg)



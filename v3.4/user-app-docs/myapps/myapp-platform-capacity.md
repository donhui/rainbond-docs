---
title: 扩容
summary: 用户可以根据应用当前的访问情况、压力大小等实际情况，动态的调整后端服务节点的数量和配置大小进行扩容。
toc: false
---

&emsp;&emsp;用户可以根据应用当前应用的使用情况、负载能力等，动态的调整后端服务节点的数量或调整内存进行扩容。如增大内存-垂直升级，添加多个节点(实例数)-水平升级。===

<img src="https://static.goodrain.com/images/acp/docs/user-docs/myapps/myapp-platform-capacity.png" style="border:1px solid #eee;max-width:100%" />

> 为什么服务扩容和服务升级可以动态的完成，不影响服务？
>
> &emsp;&emsp;所谓动态扩容，即指不影响当前服务，可以随时调整节点数，扩容内存大小。平台会给每个服务自动配置一个负载均衡资源池，扩容时，平台会增加新的节点到资源池中，原节点保持服务，调整内存时，平台会将新的节点加入到资源池中，当老的节点链接断开后，负载均衡即将其下线。
>
> &emsp;&emsp;而对于动态升级，负载均衡会将当前没有建立链接的节点下线更新，后续的请求都被分到更新的节点上，而老的节点在链接断开后，即被下线更新。这样可以保证服务一直可用，使升级与扩容动态完成。
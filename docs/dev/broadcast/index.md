# 关于广播
Echo-Live 中的广播是一种基于 [Broadcast Channel API](https://developer.mozilla.org/zh-CN/docs/Web/API/Broadcast_Channel_API){ target="_blank" } 的浏览器内网页之间的通信技术，利用此技术可以实现在 OBS 的自定义浏览器停靠窗口向场景中的浏览器源发送数据的功能。

在 Echo-Live 中，由 `EchoLiveBroadcast` 类负责处理广播消息。

Echo-Live 提供了一些广播接口，详情请通过本文档目录查阅。

## :material-sign-direction: 会话流程
### :material-application-outline: 客户端
1. 加入频道后，发送 [`hello`](api/hello.md) 消息。
2. 离开频道前，发送 [`close`](api/close.md) 消息。

### :material-server: 服务端
1. 加入频道后，发送 [`ping`](api/ping.md) 消息。
2. 收到客户端发来的 [`hello`](api/hello.md) 消息时，登记其 UUID 以便于管理。
3. 收到客户端发来的 [`close`](api/hello.md) 消息时，将其 UUID 从登记列表中移除。
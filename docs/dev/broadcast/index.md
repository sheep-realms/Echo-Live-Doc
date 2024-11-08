# 关于广播
Echo-Live 中的广播是一种基于 [Broadcast Channel API](https://developer.mozilla.org/zh-CN/docs/Web/API/Broadcast_Channel_API){ target="_blank" } 的浏览器内网页之间的通信技术，利用此技术可以实现在 OBS 的自定义浏览器停靠窗口向场景中的浏览器源发送数据的功能。

在 Echo-Live 中，由 `EchoLiveBroadcast` 类负责处理广播消息。

Echo-Live 提供了一些广播接口，详情请通过本文档目录查阅。

另外，Echo-Live 还提供了一些 :material-test-tube:{ .color-indigo } 实验性 API，使用这些 API 需要将配置项 `echolive.experimental_api_enable` 设为 `true`。

## :material-connection: 使用 WebSocket 接口

当配置项 `echolive.broadcast.websocket_enable` 设为 `true` 时将会启用 Echo-Live 的 WebSocket 接口，当配置项 `editor.websocket.enable` 设为 `true` 时将会启用编辑器的 WebSocket 接口。

它们会在加载时立即尝试连接到配置项 `websocket_url` 中指定的 WebSocket 服务器。

连接成功后，客户端会立即发送 [`hello`](api/hello.md) 消息，编辑器会立即发送 [`ping`](api/ping.md) 消息。

如果连接失败，Echo-Live 终端会尝试重连，最大尝试重连次数由配置定义，默认为 5 次。除非收到 [`websocket_close`](api/websocket_close.md) 消息，Echo-Live 终端会在连接中断时尝试重连。

WebSocket 接口直接对接到广播，因此可以通过 WebSocket 使用广播 API。通过 WebSocket 发送 JSON 消息之前，需要使用类似于 `JSON.stringify` 的方法将其序列化为字符串。

Echo-Live 终端可以通过 WebSocket 接口接收字符串（`String`）数据和二进制（`Blob`）数据。

## :material-sign-direction: 会话流程
### :material-application-outline: 客户端
1. 加入频道后，发送 [`hello`](api/hello.md) 消息。
2. 离开频道前，发送 [`close`](api/close.md) 消息。

### :material-server: 服务端
1. 加入频道后，发送 [`ping`](api/ping.md) 消息。
2. 收到客户端发来的 [`hello`](api/hello.md) 消息时，登记其 UUID 以便于管理。
3. 收到客户端发来的 [`close`](api/hello.md) 消息时，将其 UUID 从登记列表中移除。

## :material-code-braces-box: 广播类
Echo-Live 广播系统由以下几个类组成：

| 类名 | 父类 | 描述 |
| - | - | - |
| `EchoLiveBroadcast` | | 基类。 |
| `EchoLiveBroadcastServer` | `EchoLiveBroadcast` | 服务器。 |
| `EchoLiveBroadcastClient` | `EchoLiveBroadcast` | 客户端。 |
| `EchoLiveBroadcastPortal` | `EchoLiveBroadcastClient` | 对话框。 |
| `EchoLiveBroadcastHistory` | `EchoLiveBroadcastClient` | 历史记录浏览器。 |
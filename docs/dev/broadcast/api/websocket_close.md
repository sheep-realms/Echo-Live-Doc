# websocket_close

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.3.0</span>
</span>
<span class="feature-tag" title="出站终端类型" markdown>
    <span class="icon">:material-arrow-up:</span>
    <span class="text">WebSocket 服务器</span>
</span>
<span class="feature-tag" title="入站终端类型" markdown>
    <span class="icon">:material-arrow-down:</span>
    <span class="text">所有客户端</span>
</span>

关闭 Echo-Live 客户端的 WebSocket 连接。

## :material-send: 发送数据
此动作不需要发送任何数据。
S
``` javascript title="示例"
{
    action: 'websocket_close',
    /* 这里省略了一部分头部信息 */
    data: {}
}
```
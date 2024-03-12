# error

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.3.0</span>
</span>
<span class="feature-tag" title="终端类型" markdown>
    <span class="icon">:material-application-braces:</span>
    <span class="text">所有终端</span>
</span>

Echo-Live 终端发送已知错误的错误报告。

## :material-send: 发送数据
| 键名 | 类型 | 预期值 | 描述 |
| - | - | - | - |
| `name` | String | 错误名称 | 内部已捕获的错误名称。 |
| ... | ... | ... | 更多错误相关信息... |

``` javascript title="示例：WebSocket 消息解析错误"
{
    action: 'error',
    /* 这里省略了一部分头部信息 */ 
    data: {
        name: 'websocket_message_error'
    }
}
```

``` javascript title="示例：WebSocket 连接失败尝试重连"
{
    action: 'error',
    /* 这里省略了一部分头部信息 */ 
    data: {
        name: 'websocket_error',
        url: 'ws://127.0.0.1:3000',
        tryReconnect: true,
        reconnectCount: 1
    }
}
```
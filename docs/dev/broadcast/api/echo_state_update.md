# echo_state_update

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.3.0</span>
</span>
<span class="feature-tag" title="终端类型" markdown>
    <span class="icon">:material-application-braces:</span>
    <span class="text">对话框</span>
</span>

Echo-Live 客户端更新 Echo 状态。

## :material-send: 发送数据
| 键名 | 类型 | 预期值 | 描述 |
| - | - | - | - |
| `state` | String | 状态名称 | Echo 的运行状态名称。 |
| `messagesCount` | Number | 剩余消息数 | Echo 消息队列中剩余的消息数。 |

`state` 参数应当是以下值：

| 值 | 描述 |
| - | - |
| `ready` | 新消息已准备就绪，未开始打印。通常情况下这个状态持续时间非常短。 |
| `play` | 打印开始。 |
| `stop` | 打印结束。 |

注：Echo 在打印结束前最后一个字符完成打印时为 `last` 状态，但直到状态变为 `stop` 之前不会触发任何事件且间隔时间极短，因此该状态值被忽略。

``` javascript title="示例"
{
    action: 'echo_state_update',
    /* 这里省略了一部分头部信息 */ 
    data: {
        state: 'play',
        messagesCount: 0
    }
}
```
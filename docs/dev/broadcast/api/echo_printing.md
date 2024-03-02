# echo_printing

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.3.0</span>
</span>
<span class="feature-tag" title="终端类型" markdown>
    <span class="icon">:material-application-braces:</span>
    <span class="text">对话框</span>
</span>

Echo-Live 对话框客户端向历史记录客户端发送正在打印的消息。

## :material-send: 发送数据
| 键名 | 类型 | 预期值 | 描述 |
| - | - | - | - |
| `uuid` | String | UUID | 客户端自己的 UUID。 |
| `username` | String | 说话人 | Echo-Live 对话框中显示的说话人。 |
| `message` | String | 消息 | Echo 当前正在打印的**单条**消息的纯文本。 |

``` javascript title="示例"
{
    action: 'error',
    target: undefined,
    type: 'live',
    data: {
        uuid: '2c3103f0-b4ec-4041-b17a-a3d5d19d515a',
        username: '【说话人】',
        message: '这里是说话内容。'
    }
}
```
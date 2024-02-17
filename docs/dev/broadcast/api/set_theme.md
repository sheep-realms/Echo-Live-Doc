# set_theme

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.2.5</span>
</span>
<span class="feature-tag" title="终端类型" markdown>
    <span class="icon">:material-application-braces:</span>
    <span class="text">服务器</span>
</span>

设置 Echo-Live 的主题。

## :material-send: 发送数据
| 键名 | 类型 | 预期值 | 描述 |
| - | - | - | - |
| `name` | String | 主题名称 | 已定义的主题名称。 |

``` javascript title="示例"
{
    action: 'set_theme',
    target: undefined,
    type: 'server',
    data: {
        name: 'bubble'
    }
}
```
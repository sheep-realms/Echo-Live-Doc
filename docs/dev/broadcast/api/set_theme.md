# set_theme
:material-tag:{ title="最早可用版本" .color-indigo } <span class="text-version">1.2.5</span>

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
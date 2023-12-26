# hello
:material-tag:{ title="最早可用版本" .color-indigo } <span class="text-version">1.2.2</span>

Echo-Live 客户端加入频道广播或响应服务端 [`ping`](ping.md) 广播。响应服务端 `ping` 广播时需要指定 `target`。

## :material-send: 发送数据
| 键名 | 类型 | 预期值 | 描述 |
| - | - | - | - |
| `uuid` | String | UUID | 客户端自己的 UUID。 |
| `hidden` | Boolean | 布尔值 | 客户端网页是否不可见。 |

``` javascript title="示例"
{
    action: 'hello',
    target: undefined,
    data: {
        uuid: '2c3103f0-b4ec-4041-b17a-a3d5d19d515a',
        hidden: false
    }
}
```
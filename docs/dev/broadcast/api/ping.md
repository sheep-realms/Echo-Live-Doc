# ping
:material-tag:{ title="最早可用版本" .color-indigo } <span class="text-version">1.2.2</span>

服务端加入频道时发送广播以收集在线的客户端数据。

## :material-send: 发送数据
| 键名 | 类型 | 预期值 | 描述 |
| - | - | - | - |
| `uuid` | String | UUID | 服务端自己的 UUID，客户端将以此作为回复目标。 |

``` javascript title="示例"
{
    action: 'ping',
    target: undefined,
    data: {
        uuid: '2c3103f0-b4ec-4041-b17a-a3d5d19d515a'
    }
}
```
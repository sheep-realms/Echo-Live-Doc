# ping
<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.2.2</span>
</span>
<span class="feature-tag" title="终端类型" markdown>
    <span class="icon">:material-application-braces:</span>
    <span class="text">服务器</span>
</span>

服务端加入频道时发送广播以收集在线的客户端数据。

## :material-send: 发送数据
| 键名 | 类型 | 预期值 | 描述 |
| - | - | - | - |
| `uuid` | String | UUID | 服务端自己的 UUID，客户端将以此作为回复目标。 |

``` javascript title="示例"
{
    action: 'ping',
    target: undefined,
    type: 'server',
    data: {
        uuid: '2c3103f0-b4ec-4041-b17a-a3d5d19d515a'
    }
}
```

``` javascript title="客户端回复示例"
{
    action: 'hello',
    target: '2c3103f0-b4ec-4041-b17a-a3d5d19d515a',
    type: 'live',
    data: {
        uuid: 'ee8b8e3b-e8fb-4c41-b9be-757b4add08ad',
        hidden: false
    }
}
```
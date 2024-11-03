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
此动作不需要发送任何数据。

``` javascript title="示例"
{
    action: 'ping',
    target: undefined,
    from: {
        name: '2c3103f0-b4ec-4041-b17a-a3d5d19d515a',
        uuid: '2c3103f0-b4ec-4041-b17a-a3d5d19d515a',
        type: 'server',
        timestamp: 1721491200000
    },
    data: {}
}
```

``` javascript title="客户端回复示例"
{
    action: 'hello',
    target: '2c3103f0-b4ec-4041-b17a-a3d5d19d515a',
    from: {
        name: '@example',
        uuid: 'ee8b8e3b-e8fb-4c41-b9be-757b4add08ad',
        type: 'live',
        timestamp: 1721491200123
    },
    data: {
        hidden: false
    }
}
```

## :material-history: 历史

| 版本 | 描述 |
| - | - |
| 1.2.2 | 加入了 `ping` API。 |
| 1.3.0 | 因头部信息中已包含，移除了 `uuid` 字段。 |
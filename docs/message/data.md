# 自定义数据

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.2.0</span>
</span>

Echo-Live 的段落格式中允许传递自定义数据，以实现有趣的交互。

想要传递自定义数据，可以通过 `data` 字段设置自定义数据。

``` json linenums="1" hl_lines="4"
{
    "message": {
        "text": "我们所经历的每个平凡的日常，也许就是连续发生的奇迹。",
        "data": {}
    }
}
```

`data` 字段是一个对象，可以放入任意数据。这是为开发者特意准备的功能，Echo-Live 也为其设计了一些好玩的交互。

需要注意的是，该字段与[启动参数](start-par.md)中的 `customData` 字段功能相同，如果没有在消息打印过程中传递数据的必要，请使用启动参数。

Echo-Live 已为以下自定义数据设计了交互：

| 参数名 | 预期类型 | 描述 |
| - | - | - |
| `username` | String | 变更说话人名称。 |
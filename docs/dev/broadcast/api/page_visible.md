# page_visible
<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.2.2</span>
</span>
<span class="feature-tag" title="终端类型" markdown>
    <span class="icon">:material-application-braces:</span>
    <span class="text">所有客户端</span>
</span>

Echo-Live 客户端页面重新可见时发送。

## :material-send: 发送数据
此动作不需要发送任何数据。

``` javascript title="示例"
{
    action: 'page_visible',
    /* 这里省略了一部分头部信息 */
    data: {}
}
```

## :material-history: 历史

| 版本 | 描述 |
| - | - |
| 1.2.2 | 加入了 `page_visible` API。 |
| 1.3.0 | 因头部信息中已包含，移除了 `uuid` 字段。 |
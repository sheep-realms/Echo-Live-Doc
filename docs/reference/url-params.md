# URL 参数

Echo-Live 部分页面支持传递 URL 参数，以单独实现特定效果。

如果您不知道什么是 URL 参数，请参阅 MDN 上的《[什么是 URL？](https://developer.mozilla.org/zh-CN/docs/Learn/Common_questions/Web_mechanics/What_is_a_URL#%E5%8F%82%E6%95%B0){ target="_blank" }》。本文简而言之：URL 地址中可以传递一些参数，包含参数名（键）和参数值，以问号 `?` 作为参数列表的开始，以 `&` 符号分隔的键/值对列表。如下所示：

```
http://example.com/hello.html?参数名=参数值
http://example.com/hello.html?参数名=参数值&另一个参数名=另一个参数值
```

例如，您可以为某个对话框单独设置主题为 `void`，您在 OBS 中应当为对应的浏览器源的 URL 设置为如下内容：

```
file:///D:/Echo-Live/live.html?theme=void
```

其中，`theme` 就是参数名，在这里表示指定主题。前面的地址是 `live.html` 这个文件在您的设备中的地址，请根据实际情况修改。


## 参数列表

| 参数名 | 描述 | 可用范围 |
| - | - | - |
| `name` | 对话框的识别名。 | 对话框（`live.html`） |
| `targeted` | 仅接收定向广播，填写任意内容即可生效。 | 对话框（`live.html`） |
| `theme` | 设置主题。可用的主题请见[主题列表](../custom/theme.md#theme-list)。 | 对话框（`live.html`）和历史记录（`history.html`） |
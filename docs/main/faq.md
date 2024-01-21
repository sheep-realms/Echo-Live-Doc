# 常见问题

## :material-alert-decagram: 重要问题

### :material-file-edit: 如何编辑文件内容？

如果您想要编辑 JS、CSS、HTML 等文件的内容，建议您使用专业的文本编辑器，例如 [VSCode](https://code.visualstudio.com/)、[Sublime Text](https://www.sublimetext.com/)。

**不 要 使 用 记 事 本！**

### :material-file-eye: 如何显示文件扩展名？

本文档默认您已开启文件扩展名显示，您可能会疑惑：

> `live.html`、`editor.html` 都是什么东西啊？我只看到了了 `live` 和 `editor`！

如果您有这样的疑惑，说明您没有开启文件扩展名显示。

如果您是 Windows 10 ~ 11 操作系统，请打开文件资源管理器（桌面上的 “此电脑”），点击上方的 “查看” 菜单，找到 “显示/隐藏” 分组，勾选 “文件扩展名”。

![显示文件扩展名操作演示](../image/faq/file_extension.png){ .img-light-hyper }

如果您是其他的操作系统，抱歉我手里没有这样的系统，请您自己上网搜索教程。


## :material-pencil: 编辑器相关

### 如何编辑富文本消息？

目前暂不支持可视化富文本编辑。在广播模式下，您可以使用[快速格式化代码](../message/formatting-code.md)或在编辑器的 输出 > 输出内容 标签页中编辑自定义[消息格式](../message/index.md)代码并发送。

例如，您可以将以下代码粘贴到输出内容文本框中：

``` javascript linenums="1"
{
    "username": "【测试】",
    "messages": [
        {
            "message": "你好，世界！",
            "style": {
                "bold": true
            }
        }
    ]
}
```

点击下方的 “发送” 按钮，您将会在对话框中看到粗体的 “你好，世界！” 消息。如果格式错误，日志标签页中会显示醒目错误提示。

### 如何一次性发送多条消息？

这一般用于预先准备好的演出，请不要尝试在直播中即兴发挥，很麻烦的！

首先您需要准备好消息格式代码，请参考[消息队列](../message/message-list.md)。

在广播模式下，您可以在编辑器的 输出 > 输出内容 标签页中发送自定义消息，在输出内容文本框中粘贴您准备好的代码，点击 “发送” 按钮即可。

在轮询模式下，您需要编辑 [start.js](../message/index.md) 文件，替换其中的消息格式代码。

如果操作正确，您会在对话框中看到第一条消息。在 OBS 中选中对话框源，点击 “交互” 操作按钮，在弹出的浏览器窗口中点击对话框的任意位置即可显示下一条消息，直到所有消息都已显示。


## :material-message-text: 对话框相关

### 如何修改对话框加载时显示的第一条消息？

对话框显示的第一条消息由 [start.js](../message/index.md) 脚本文件定义，如果您想要让第一条消息为空，请直接将此文件全文内容替换为：

``` javascript linenums="1"
echolive.send({
    "username": "",
    "messages": [
        {
            "message": ""
        }
    ]
});
```
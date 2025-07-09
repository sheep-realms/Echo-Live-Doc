# message_data

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.2.1</span>
</span>
<span class="feature-tag" title="出站终端类型" markdown>
    <span class="icon">:material-arrow-up:</span>
    <span class="text">服务器</span>
</span>
<span class="feature-tag" title="入站终端类型" markdown>
    <span class="icon">:material-arrow-down:</span>
    <span class="text">对话框</span>
</span>

发送消息。

## :material-send: 发送数据
此动作发送的数据是类似于 `start.js` 中的[消息格式](/message/)。

``` javascript title="示例"
{
    action: 'message_data',
    /* 这里省略了一部分头部信息 */ 
    data: {
        username: "【说话人】",
        messages: [
            {
                "message": "这里是说话内容。"
            }
        ]
    }
}
```
# message_data
:material-tag:{ title="最早可用版本" .color-indigo } <span class="text-version">1.2.1</span>

发送消息。

## :material-send: 发送数据
此动作发送的数据是类似于 `start.js` 中的[消息格式](/message/)。

``` javascript title="示例"
{
    action: 'message_data',
    target: undefined,
    type: 'server',
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
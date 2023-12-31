# 事件
:material-tag:{ title="最早可用版本" .color-indigo } <span class="text-version">1.1.4</span>

Echo-Live 的段落格式中允许定义自定义事件以触发一些有趣的动效，详见[事件列表](../custom/event.md)。

想要触发事件，可以通过 `event` 字段指定事件。

``` json linenums="1" hl_lines="4"
{
    "message": {
        "text": "我们所经历的每个平凡的日常，也许就是连续发生的奇迹。",
        "event": "shout"
    }
}
```

上面的示例中，消息会在被打印之前触发 `shout` 事件，使对话框震动。
# 基本段落格式

每一条消息中，必须包含一个 `message` 值，它可以是字符串，如下所示：

``` json linenums="1"
{
    "message": "我们所经历的每个平凡的日常，也许就是连续发生的奇迹。"
}
```

这样，一条最简单的消息完成了。上面的例子是**段落格式**的最简单的格式，将其装入**消息格式**中则应该是这样的：

``` json linenums="1" hl_lines="4 5 6"
{
    "username": "【说话人】",
    "messages": [
        {
            "message": "我们所经历的每个平凡的日常，也许就是连续发生的奇迹。"
        }
    ]
}
```

**消息格式**是一种可以直接被 Echo-Live 接受的输入格式，在广播模式下，您可以在编辑器的 输出 > 输出内容 标签页中粘贴上面的代码并发送。

实际上，这已经可以满足绝大多数需求了，并且如果您只需要最简单的格式的话，编辑器可以自动帮你完成消息格式的编写，不需要您自己写代码。我想您应该不会想着在快节奏的直播活动中搞什么繁琐复杂的富文本吧？

在编辑器的 编辑器 标签页中，您可以使用[快速格式化代码](formatting-code.md)来制作简单的文本样式。

富文本更适合用于预先准备好的演出，如新主播开播时的自我介绍、录播等使用场景。如果您没有这样的需求，那您对于消息格式的学习可以到此为止了。如果以后我们把富文本编辑器做完了，我想您也不愿意徒手编辑 JSON，作者我也不愿意。
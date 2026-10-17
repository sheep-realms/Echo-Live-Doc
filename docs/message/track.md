# 子轨道

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.9.0</span>
</span>

Echo-Live 可以创建子轨道来实现多条轨道同时打印。

要实现子轨道，可以通过段落格式的 `track` 字段设置子轨道。

``` json linenums="1" hl_lines="3 4 5 6 7"
{
    "message": "我们所经历的每个平凡的日常，也许就是连续发生的奇迹。",
    "track": [
        {
            "message": "日々私たちが過ごしている日常は、実は、奇跡の連続なのかもしれない。"
        }
    ]
}
```

子轨道是一个可包含多个段落格式的数组，这意味着您可以创建多条子轨道。

子轨道也可以使用样式、停顿、模拟打字等功能，但事件、部分自定义数据不可用。

不过请注意，子轨道不允许嵌套子轨道，因此子轨道中的 `track` 字段是无效的。

您可以通过为子轨道设置更小的字号使其看起来像是与主轨道的对译。

``` json linenums="1" hl_lines="8"
{
    "message": "我们所经历的每个平凡的日常，也许就是连续发生的奇迹。",
    "track": [
        {
            "message": {
                "text": "日々私たちが過ごしている日常は、実は、奇跡の連続なのかもしれない。",
                "style": {
                    "size": "small"
                }
            }
        }
    ]
}
```
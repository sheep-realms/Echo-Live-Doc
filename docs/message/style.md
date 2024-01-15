# 文本样式

从这一步开始，我们需要修改一下 `message` 的内容格式：

``` json linenums="1"
{
    "message": {
        "text": "我们所经历的每个平凡的日常，也许就是连续发生的奇迹。"
    }
}
```

其中，`text` 表示文本内容。在开始为其添加样式参数之前，这么做实际上等效于[基本格式](base.md)中的效果。

现在，我们要在 `message` 字段中写入 `style` 字段，这是定义文本样式的字段。

``` json linenums="1" hl_lines="4"
{
    "message": {
        "text": "我们所经历的每个平凡的日常，也许就是连续发生的奇迹。",
        "style": {}
    }
}
```

接下来，我们将围绕 `style` 字段展示其独特功能。

!!! note "开发者注意事项"

    Echo 本身并不具备解析样式的功能，也并未规定如何定义样式，样式的解析是由下游脚本实现的，是 Echo-Live 承担了这一工作。

## :material-format-bold::material-format-italic::material-format-underline::material-format-strikethrough: 粗体、斜体、下划线和删除线
`style` 字段可以定义粗体 `bold`、斜体 `italic`、下划线 `underline` 和删除线 `strikethrough`，这些值都是布尔值，把他们一股脑加进去是这样的：

``` json linenums="1" hl_lines="5 6 7 8"
{
    "message": {
        "text": "我们所经历的每个平凡的日常，也许就是连续发生的奇迹。",
        "style": {
            "bold": true,
            "italic": true,
            "underline": true,
            "strikethrough": true
        }
    }
}
```

当然一般情况下不需要加这么多，除非你在搞什么抽象艺术。

## :material-palette: 文本颜色
文本颜色可以通过 `color` 字段定义，这是一个字符串，可以接受

- `red`、`green` 等颜色关键字；
- 十六进制（如 `#66CCFF`）；
- RGB（如 `rgb(128, 128, 128)`）；
- HSL（如 `hsl(150, 30%, 60%)`）等。
  
当然还有 HWB、LAB、LCH、Oklab、Oklch 等一切能在网页上使用的颜色值表达，我不建议您玩这么花。

关于颜色值的格式详见：[&lt;color&gt; - CSS：层叠样式表 | MDN](https://developer.mozilla.org/zh-CN/docs/Web/CSS/color_value){ target="_blank" }

``` json linenums="1" hl_lines="5"
{
    "message": {
        "text": "我们所经历的每个平凡的日常，也许就是连续发生的奇迹。",
        "style": {
            "color": "#66CCFF"
        }
    }
}
```

## :material-lightbulb-on: 自定义样式
如何您想尝试自定义样式，请先学习 [CSS](https://www.runoob.com/css/css-tutorial.html){ target="_blank" }。

您可以通过 `style` 字段为文本段落写入自定义样式。是的，你没看错，是 `style` 中的 `style`...... 好吧这个套娃确实有点奇怪。

如果您已经掌握了 CSS，那我们直接上示例，这不难理解：

``` json linenums="1" hl_lines="5"
{
    "message": {
        "text": "我们所经历的每个平凡的日常，也许就是连续发生的奇迹。",
        "style": {
            "style": "font-size: 0.75em; color: #66CCFF;"
        }
    }
}
```
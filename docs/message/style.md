---
tags:
  - 斜体
  - 粗体
  - 下划线
  - 删除线
  - 颜色
  - 背景颜色
  - 字号
  - 字重
  - 着重号
  - 字间距
  - 字形伸缩
  - 自定义文本样式
---

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

## :material-format-bold::material-format-italic::material-format-underline::material-format-strikethrough: 粗体、斜体、下划线和删除线 { id="bold-italic-underline-strikethrough" }
`style` 字段可以定义粗体 `bold`、斜体 `italic`、下划线 `underline` 和删除线 `strikethrough`，这些值都是布尔值，把他们一股脑加进去是这样的：

=== "代码"

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

=== "效果预览"

    <b><i><u><s>我们所经历的每个平凡的日常，也许就是连续发生的奇迹。</b></i></u></s>

当然一般情况下不需要加这么多，除非你在搞什么抽象艺术。

## :material-palette: 文本颜色 { id="color" }
文本颜色可以通过 `color` 字段定义，这是一个字符串，可以接受：

- `red`、`green` 等颜色关键字；
- 十六进制（如 `#66CCFF`）；
- RGB（如 `rgb(128, 128, 128)`）；
- HSL（如 `hsl(150, 30%, 60%)`）等。
  
当然还有 HWB、LAB、LCH、Oklab、Oklch 等一切能在网页上使用的颜色值表达，我不建议您玩这么花。

关于颜色值的格式详见：[&lt;color&gt; - CSS：层叠样式表 | MDN](https://developer.mozilla.org/zh-CN/docs/Web/CSS/color_value){ target="_blank" }

=== "代码"

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

=== "效果预览"

    <span style="color: #66CCFF;">我们所经历的每个平凡的日常，也许就是连续发生的奇迹。</span>

## :material-palette: 背景颜色 { id="background-color" }

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.3.0</span>
</span>

文本颜色可以通过 `backgroundColor` 字段定义，格式同上。

=== "代码"

    ``` json linenums="1" hl_lines="5"
    {
        "message": {
            "text": "我们所经历的每个平凡的日常，也许就是连续发生的奇迹。",
            "style": {
                "backgroundColor": "#4287ff44"
            }
        }
    }
    ```

=== "效果预览"

    <span style="background-color: #4287ff44;">我们所经历的每个平凡的日常，也许就是连续发生的奇迹。</span>

## :material-format-size: 字号 { id="size" }

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.3.0</span>
</span>

字号可以通过 `size` 字段定义，这是一个字符串，可以接受以下值：

| 值 | 描述 |
| - | - |
| `extra-small` | 特小号，0.5 倍大小。 |
| `small` | 小号，0.75 倍大小。 |
| `middle` | 中号，原始大小。 |
| `large` | 大号，1.5 倍大小。 |
| `extra-large` | 特大号，2 倍大小。 |

!!! warning "注意"

    在有多个文本段落的情况下，文本打印过程中出现更大字号的文本会使整行文本的基线突然向下移动，这个效果不太好看，这也是 Echo-Live 直到 1.3.0 版本才加入此功能的原因。

=== "代码"

    ``` json linenums="1" hl_lines="5"
    {
        "message": {
            "text": "我们所经历的每个平凡的日常，也许就是连续发生的奇迹。",
            "style": {
                "size": "large"
            }
        }
    }
    ```

=== "效果预览"

    <span style="font-size: 1.5em;">我们所经历的每个平凡的日常，也许就是连续发生的奇迹。</span>

## :material-weight: 字重 { id="weight" }

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.3.0</span>
</span>

字重是指字体的粗细字形，字重会覆盖粗体设置。

一些字体不一定支持所有字重，在指定字重缺失的情况下会就近选择可用字重。

字重可以通过 `weight` 字段定义，这是一个字符串，可以接受以下值：

| 值 | 描述 |
| - | - |
| `thin`、`hairline` | 淡体，字重 100。 |
| `extra-light`、`ultra-light` | 特细，字重 200。 |
| `light` | 细体，字重 300。 |
| `semi-light`、`demi-light` | 次细，字重 350。 |
| `regular`、`normal`、`book`、`plain` | 标准，字重 400，默认字重。 |
| `medium` | 适中，字重 500。 |
| `semi-bold`、`demi-bold` | 次粗，字重 600。 |
| `bold` | 粗体，字重 700，与上文的粗体等价。 |
| `extra-bold`、`ultra-bold` | 特粗，字重 800。 |
| `black`、`heavy` | 浓体，字重 900。 |
| `extra-black`、`ultra-black`、`extra-heavy`、`ultra-heavy` | 特浓，字重 950。 |

=== "代码"

    ``` json linenums="1" hl_lines="5"
    {
        "message": {
            "text": "我们所经历的每个平凡的日常，也许就是连续发生的奇迹。",
            "style": {
                "weight": "thin"
            }
        }
    }
    ```

=== "效果预览"

    <span style="font-weight: 100;">我们所经历的每个平凡的日常，也许就是连续发生的奇迹。</span>

## :material-dots-horizontal: 着重号 { id="emphasis" }

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.5.0</span>
</span>

着重号可以通过 `emphasis` 字段定义，这是一个布尔值，可以在文本下方添加着重号。

=== "代码"

    ``` json linenums="1" hl_lines="5"
    {
        "message": {
            "text": "我们所经历的每个平凡的日常，也许就是连续发生的奇迹。",
            "style": {
                "emphasis": true
            }
        }
    }
    ```

=== "效果预览"

    <span style="text-emphasis: dot; -webkit-text-emphasis: dot; text-emphasis-position: under; -webkit-text-emphasis-position: under;">我们所经历的每个平凡的日常，也许就是连续发生的奇迹。</span>

## :material-format-letter-spacing: 字间距 { id="letter-spacing" }

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.3.0</span>
</span>

字间距可以通过 `letterSpacing` 字段定义，这是一个字符串，可以接受以下值：

| 值 | 描述 |
| - | - |
| `compact` | 紧凑的间距，文字略微相互靠拢。 |
| `normal` | 默认间距。 |
| `four-per-width` | 四分之一字符宽度间距。 |
| `half-width` | 半角字符宽度间距。 |
| `full-width` | 全角字符宽度间距。 |

=== "代码"

    ``` json linenums="1" hl_lines="5"
    {
        "message": {
            "text": "你说话带空格。",
            "style": {
                "letterSpacing": "half-width"
            }
        }
    }
    ```

=== "效果预览"

    <span style="letter-spacing: 0.5em;">你说话带空格。</span>

## :material-format-letter-matches: 字形伸缩 { id="stretch" }

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.3.0</span>
</span>

字形伸缩可以通过 `stretch` 字段定义，这是一个字符串，可以接受以下值：

| 值 | 描述 |
| - | - |
| `ultra-condensed` | 伸缩 50%。 |
| `extra-condensed` | 伸缩 62.5%。 |
| `condensed` | 伸缩 75%。 |
| `semi-condensed` | 伸缩 87.5%。 |
| `normal` | 伸缩 100%，原始字形。 |
| `semi-expanded` | 伸缩 112.5%。 |
| `expanded` | 伸缩 125%。 |
| `extra-expanded` | 伸缩 150%。 |
| `ultra-expanded` | 伸缩 200%。 |

!!! warning "注意"

    绝大多数字体都不支持伸缩调整，包括 Echo-Live 默认使用的思源黑体。您需要自行选用支持伸缩调整的字体才能正常使用此功能。

``` json linenums="1" hl_lines="5" title="代码"
{
    "message": {
        "text": "Only my RAILGUN can shoot it.",
        "style": {
            "stretch": "condensed"
        }
    }
}
```

## :material-lightbulb-on: 自定义样式 { id="style" }

如何您想尝试自定义样式，请先学习 [CSS](https://www.runoob.com/css/css-tutorial.html){ target="_blank" }。

您可以通过 `style` 字段为文本段落写入自定义样式。是的，你没看错，是 `style` 中的 `style`...... 好吧这个套娃确实有点奇怪。

如果您已经掌握了 CSS，那我们直接上示例，这不难理解：

=== "代码"

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

=== "效果预览"

    <span style="font-size: 0.75em; color: #66CCFF;">我们所经历的每个平凡的日常，也许就是连续发生的奇迹。</span>

另外，如果您预先准备好了一些样式，您也可以通过为文本添加类（Class）属性来为其赋予样式，请注意该字段并不在 `style` 字段内：

=== "消息"

    ``` json linenums="1" hl_lines="4"
    {
        "message": {
            "text": "我们所经历的每个平凡的日常，也许就是连续发生的奇迹。",
            "class": "example-text example-text-2"
        }
    }
    ```

=== "CSS"

    ``` css linenums="1"
    .example-text {
        font-size: 0.75em;
        color: #66CCFF;
    }
    .example-text-2 {
        font-weight: bold;
    }
    ```

=== "效果预览"

    <span style="font-size: 0.75em; color: #66CCFF; font-weight: bold;">我们所经历的每个平凡的日常，也许就是连续发生的奇迹。</span>

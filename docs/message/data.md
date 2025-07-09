---
tags:
  - 表情
  - 图片
  - 行为
---

# 自定义数据

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.2.0</span>
</span>

Echo-Live 的段落格式中允许传递自定义数据，以实现有趣的交互。

想要传递自定义数据，可以通过 `data` 字段设置自定义数据。

``` json linenums="1" hl_lines="4"
{
    "message": {
        "text": "我们所经历的每个平凡的日常，也许就是连续发生的奇迹。",
        "data": {}
    }
}
```

`data` 字段是一个对象，可以放入任意数据。这是为开发者特意准备的功能，Echo-Live 也为其设计了一些好玩的交互。

需要注意的是，该字段与[启动参数](start-par.md)中的 `customData` 字段功能相同，如果没有在消息打印过程中传递数据的必要，请使用启动参数。

Echo-Live 已为以下自定义数据设计了交互：

| 参数名 | 预期类型 | 描述 |
| - | - | - |
| `action` | Object | 见[行为](#action)。 |
| `character` | Object | 见[形象](character.md)。 |
| `emoji` | String | 见[表情](#emoji)。 |
| `image` | Object | 见[图片](#image)。 |
| `username` | String | 变更说话人名称。 |


## 行为 { id="action" }

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.4.0</span>
</span>
<span class="feature-tag" title="实验性内容" markdown>
    <span class="icon">:material-test-tube:</span>
    <span class="text">实验性内容</span>
</span>

`action` 字段定义了在特定事件中所产生的行为。目前有以下事件：

| 事件名 | 描述 |
| - | - |
| `printEnd` | 消息打印结束。 |

以及以下行为：

| 行为名 | 描述 |
| - | - |
| `next` | 立即打印下一条消息。 |

用法如下：

``` json linenums="1" hl_lines="4 5 6"
{
    "message": {
        "text": "我们所经历的每个平凡的日常，也许就是连续发生的奇迹。",
        "data": {
            "printEnd": "next"
        }
    }
}
```

## 表情 { id="emoji" }

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.4.0</span>
</span>

`emoji` 字段用于在段落开头添加表情图片，填写的值是表情图片的识别名。

用法如下：

``` json linenums="1" hl_lines="4 5 6"
{
    "message": {
        "text": "←这是表情。",
        "data": {
            "emoji": "sp:happy"
        }
    }
}
```

## 图片 { id="image" }

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.4.0</span>
</span>

`image` 字段用于在段落开头添加自定义图片，有以下值：

| 参数名 | 预期类型 | 描述 |
| - | - | - |
| `url` | String | 图片的 URL，必填。 |
| `margin` | Object | 外边距。 |
| `rendering` | String | 重采样方式，可以是 `auto`（自动）和 `pixelated`（最邻近）。 |
| `size` | Object | 图片尺寸。 |

`margin` 有以下值：

| 参数名 | 预期类型 | 描述 |
| - | - | - |
| `left` | String | 左侧外边距，任何可被 CSS 接受的带单位长度值，下同。 |
| `right` | String | 右侧外边距。 |

`size` 有以下值：

| 参数名 | 预期类型 | 描述 |
| - | - | - |
| `width` | Object | 宽度。 |
| `height` | Object | 高度。 |

`size` 中的 `width` 和 `height` 有以下值：

| 参数名 | 预期类型 | 描述 |
| - | - | - |
| `value` | String | 值，任何可被 CSS 接受的带单位长度值，下同。 |
| `max` | String | 最大值。 |
| `min` | String | 最小值。 |

需要注意的是，`url` 可以是绝对地址，如：

```
file:///D:/Echo-Live/res/image/emoji/sheep-realms/pixel-head/000_default.png"
```

也可以是相对地址，如：

```
res/image/emoji/sheep-realms/pixel-head/000_default.png"
```

甚至可以是 Data URL。

完整用法如下：

``` json linenums="1"
{
    "message": {
        "text": "←这是图片。",
        "data": {
            "image": {
                "url": "res/image/emoji/sheep-realms/pixel-head/000_default.png",
                "margin": {
                    "left": "0em",
                    "right": "0em"
                },
                "rendering": "pixelated",
                "size": {
                    "height": {
                        "max": "5em",
                        "min": "0em"
                    },
                    "width": {
                        "max": "5em",
                        "min": "0em"
                    }
                }
            }
        }
    }
}
```
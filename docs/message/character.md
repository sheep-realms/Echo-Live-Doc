# 形象

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.6.0</span>
</span>
<span class="feature-tag" title="实验性内容" markdown>
    <span class="icon">:material-test-tube:</span>
    <span class="text">实验性内容</span>
</span>

Echo-Live 的段落格式可以向 Echo-Live 内置的形象播放器发出指令，控制其显示的形象、动作和镜头。

想要传递形象数据，可以在[自定义数据](data.md)中添加 `character` 字段。

=== "精简格式"

    ``` json linenums="1"
    "character": {
        "avatar": {
            "name": "echo_otone",
            "action": "idle",
            "scene": "full"
        }
    }
    ```

=== "自定义格式"

    ``` json linenums="1"
    "character": {
        "custom": false,
        "image": {
            "url": "/* URL */",
            "position": "/* CSS background-position */",
            "size": "/* CSS background-size */",
            "repeat": "/* CSS background-repeat */"
        },
        "effect": {
            "name": "fade-in",
            "duration": 250,
            "scale": 1,
            "timingFunction": "ease-out"
        }
    }
    ```

## 字段列表

| 字段名 | 类型 | 描述 |
| - | - | - |
| `custom` | Boolean | 是否启用自定义格式。 |
| `avatar` | Object | 形象数据，精简格式必要。 |
| `avatar.name` | String | 形象名称。 |
| `avatar.action` | String | 动作名称，可选。 |
| `avatar.scene` | String | 镜头名称，可选。 |
| `image` | Object | 图像数据。 |
| `image.url` | String | 图像 URL。 |
| `image.position` | String | CSS 属性，控制图片位置。 |
| `image.size` | String | CSS 属性，控制图片尺寸。 |
| `image.repeat` | String | CSS 属性，控制图片重复填充方式。 |
| `effect` | Object | 图像切换动效，无论是精简格式还是自定义格式都可用。 |
| `effect.name` | String | 动效名称。 |
| `effect.duration` | Number | 动效用时。 |
| `effect.scale` | Number | 动效规模乘数。 |
| `effect.timingFunction` | String | 动效时间曲线。 |
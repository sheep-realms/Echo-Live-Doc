# 关于主题

<style>
    .theme-review {
        box-shadow: var(--md-default-fg-color--lightest) 0 0 16px;
    }
</style>

Echo-Live 内置了多套主题，您可以通过修改 `live.html` 中定义主题样式的部分修改主题，文件中已有注释指引。您可以通过 `res/style/live-theme/` 文件夹浏览可用主题。

另外，各种主题文件中都在顶部整理了常用变量，方便您快速修改诸如背景颜色、边框、字体大小等参数。

主题文件使用的是广泛运用的 CSS 样式，如有需要，您可以咨询网页或UI设计师定制主题。

## 修改主题的方法
在 `live.html` 文件中您可用看到以下被注释强调的内容：

``` html linenums="1" hl_lines="2"
<!-- ↓ 这里是主题样式，如需替换请修改这里的 href 值 -->
<link id="echo-live-theme" rel="stylesheet" href="res/style/live-theme/vanilla.css">
<!-- ↑ 这里是主题样式，请通过 res/style/live-theme/ 文件夹浏览可用主题 -->
```

假如您想将主题文件更换为 `bubble.css`，您应当如此修改：

``` html linenums="1" hl_lines="2"
<!-- ↓ 这里是主题样式，如需替换请修改这里的 href 值 -->
<link id="echo-live-theme" rel="stylesheet" href="res/style/live-theme/bubble.css">
<!-- ↑ 这里是主题样式，请通过 res/style/live-theme/ 文件夹浏览可用主题 -->
```

最后，别忘了保存文件。

## 主题介绍
| :material-file: 文件名 | :material-tag: 名称 | :material-help-circle: 描述 |
| - | - | - |
| vanilla.css | 原版 | Echo-Live 的默认主题，几乎没有任何装饰，适用于在画面中以全屏宽度靠下展现。右侧预留了立绘位置，可将立绘覆盖在对话框之上。 |
| bubble.css | 气泡 | 常见的气泡对话框，具有粗边框和投影，可调整成任意尺寸，没有预留立绘位置。 |
| vold.css | 虚空 | 无背景对话框，仅显示文字。 |

## 主题预览
### 原版 | Vanilla

![Vanilla](../image/theme/vanilla.jpg){ .theme-review }

### 气泡 | Bubble

![Bubble](../image/theme/bubble.jpg){ .theme-review }
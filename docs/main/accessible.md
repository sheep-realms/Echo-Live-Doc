# 无障碍使用指南

!!! aria "欢迎阅读无障碍使用指南！"
    我们尊重每一位用户，尽可能满足所有用户的需求。我们对暂时无法满足需求的用户致以歉意，我们对所有人的崇高理想深表敬意。

## :material-account-voice: 讲述人适配

完成度：仍需改进。

Echo-Live 编辑器配置了一些 ARIA 属性，即无障碍富互联网应用（Accessible Rich Internet Applications）。我们已尽力改善视障人士的使用体验，但仍未达到我们预期的效果。我们对此没有任何经验，如果您可以提供帮助，欢迎联系我们改进。

## :material-keyboard: 键盘可访问

完成度：良好。

Echo-Live 编辑器是键盘可访问的，没有死区、不可达的交互元素。

使用 Alt + 数字键 组合键可以快速切换标签页。

## :material-palette: 色盲/色弱视觉调整

完成度：良好。

Echo-Live 编辑器中存在一些可能会使色盲/色弱人士无法辨别的元素，我们在配置文件 config.js 中提供了一些配置以解决这些问题，这些配置被放置在 accessible 配置项中，内容如下：

| 配置名称 | 描述 |
| - | - |
| high_contrast | 高对比度。 |
| drotanopia_and_deuteranopia | 红绿色盲。 |

您可以将这些配置值设为 true 以启用相关调整。
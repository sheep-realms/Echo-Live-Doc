# set_theme_style_url
:material-tag:{ title="最早可用版本" .color-indigo } <span class="text-version">1.2.5</span> :material-test-tube:{ title="实验性 API" .color-indigo } <span class="text-version">实验性 API</span>

设置 Echo-Live 的主题样式文件 URL。

这不是一个最佳解决方案，请使用 [`set_theme`](set_theme.md)。

## :material-send: 发送数据
| 键名 | 类型 | 预期值 | 描述 |
| - | - | - | - |
| `url` | String | URL | 样式文件的 URL 地址。 |

``` javascript title="示例"
{
    action: 'set_theme_style_url',
    target: undefined,
    type: 'server',
    data: {
        url: 'res/style/live-theme/bubble.css'
    }
}
```
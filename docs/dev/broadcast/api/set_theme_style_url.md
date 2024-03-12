# set_theme_style_url

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.2.5</span>
</span>
<span class="feature-tag" title="终端类型" markdown>
    <span class="icon">:material-application-braces:</span>
    <span class="text">服务器</span>
</span>
<span class="feature-tag" title="实验性 API" markdown>
    <span class="icon">:material-test-tube:</span>
    <span class="text">实验性 API</span>
</span>

设置 Echo-Live 的主题样式文件 URL。

这不是一个最佳解决方案，请使用 [`set_theme`](set_theme.md)。

## :material-send: 发送数据
| 键名 | 类型 | 预期值 | 描述 |
| - | - | - | - |
| `url` | String | URL | 样式文件的 URL 地址。 |

``` javascript title="示例"
{
    action: 'set_theme_style_url',
    /* 这里省略了一部分头部信息 */
    data: {
        url: 'res/style/live-theme/bubble.css'
    }
}
```
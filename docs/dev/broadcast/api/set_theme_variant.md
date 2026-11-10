# set_theme_variant

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.9.3</span>
</span>
<span class="feature-tag" title="出站终端类型" markdown>
    <span class="icon">:material-arrow-up:</span>
    <span class="text">服务器</span>
</span>
<span class="feature-tag" title="入站终端类型" markdown>
    <span class="icon">:material-arrow-down:</span>
    <span class="text">所有客户端</span>
</span>

设置 Echo-Live 的主题。

## :material-send: 发送数据
| 键名 | 类型 | 预期值 | 描述 |
| - | - | - | - |
| `name` | String | 主题变体名称 | 已定义的主题变体名称。 |

``` javascript title="示例"
{
    action: 'set_theme_variant',
    /* 这里省略了一部分头部信息 */
    data: {
        variant_name: 'azure'
    }
}
```
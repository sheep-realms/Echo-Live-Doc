# set_live_display

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.5.0</span>
</span>
<span class="feature-tag" title="终端类型" markdown>
    <span class="icon">:material-application-braces:</span>
    <span class="text">服务器</span>
</span>

设置 Echo-Live 客户端显示状态。

## :material-send: 发送数据
| 键名 | 类型 | 预期值 | 描述 |
| - | - | - | - |
| `display` | Boolean | 布尔值 | Echo-Live 是否处于显现状态。 |

``` javascript title="示例"
{
    action: 'set_live_display',
    /* 这里省略了一部分头部信息 */ 
    data: {
        display: true
    }
}
```
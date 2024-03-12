# hello

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.2.2</span>
</span>
<span class="feature-tag" title="终端类型" markdown>
    <span class="icon">:material-application-braces:</span>
    <span class="text">所有客户端</span>
</span>

Echo-Live 客户端加入频道广播或响应服务端 [`ping`](ping.md) 广播。响应服务端 `ping` 广播时需要指定 `target`。

## :material-send: 发送数据
| 键名 | 类型 | 预期值 | 描述 |
| - | - | - | - |
| `hidden` | Boolean | 布尔值 | 客户端网页是否不可见。 |

``` javascript title="示例"
{
    action: 'hello',
    /* 这里省略了一部分头部信息 */ 
    data: {
        hidden: false
    }
}
```
# shutdown

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.4.0</span>
</span>
<span class="feature-tag" title="出站终端类型" markdown>
    <span class="icon">:material-arrow-up:</span>
    <span class="text">服务器</span>
</span>
<span class="feature-tag" title="入站终端类型" markdown>
    <span class="icon">:material-arrow-down:</span>
    <span class="text">所有客户端</span>
</span>

终止客户端运行。

## :material-send: 发送数据
| 键名 | 类型 | 预期值 | 描述 |
| - | - | - | - |
| `reason` | String | 理由 | 供错误追踪使用。 |

``` javascript title="示例"
{
    action: 'shutdown',
    /* 这里省略了一部分头部信息 */
    data: {
        reason: '理由'
    }
}
```
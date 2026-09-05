# editor_typing

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.8.7</span>
</span>
<span class="feature-tag" title="出站终端类型" markdown>
    <span class="icon">:material-arrow-up:</span>
    <span class="text">服务器</span>
</span>
<span class="feature-tag" title="入站终端类型" markdown>
    <span class="icon">:material-arrow-down:</span>
    <span class="text">对话框</span>
</span>

在编辑器中输入消息时会通过此 API 发送心跳包，每隔 1.5 秒发送一次。

## :material-send: 发送数据
| 键名 | 类型 | 预期值 | 描述 |
| - | - | - | - |
| `username` | String | 用户名 | 用于在输入提示消息中显示说话人。 |

``` javascript title="示例"
{
    action: 'hello',
    /* 这里省略了一部分头部信息 */ 
    data: {
        username: '追音'
    }
}
```
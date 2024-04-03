# error_unknow

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.3.0</span>
</span>
<span class="feature-tag" title="终端类型" markdown>
    <span class="icon">:material-application-braces:</span>
    <span class="text">所有客户端</span>
</span>

Echo-Live 客户端发送未捕获错误的错误报告。

关于捕获的错误信息，通常通过 [Error](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Error){ target="_blank" } 对象获取。

## :material-send: 发送数据
| 键名 | 类型 | 预期值 | 描述 |
| - | - | - | - |
| `message` | String | 错误消息 | 错误事件的消息或包含堆栈的消息。 |
| `source` | String | 源文件名 | 发生错误的文件。 |
| `line` | Number | 行号 | 错误所在行号。 |
| `col` | Number | 列号 | 错误所在列号。 |

``` javascript title="示例"
{
    action: 'error_unknow',
    /* 这里省略了一部分头部信息 */ 
    data: {
        message: 'SyntaxError: Missing initializer in const declaration\n    at <anonymous>:3:8',
        source: 'file:///C:/foo/bar/live.html',
        line: 1,
        col: 7
    }
}
```
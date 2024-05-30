# shutdown

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.4.0</span>
</span>
<span class="feature-tag" title="限制条件" markdown>
    <span class="icon">:material-broadcast:</span>
    <span class="text">仅限广播模式</span>
</span>

发送 [`shutdown`](../broadcast/api/shutdown.md) 广播，终止客户端运行。

## 语法

`shutdown [<原因>]`

## 参数

- `<原因>`
    - 任意文本。

## 效果

| 命令 | 触发条件 | 结果 |
| - | - | - |
| 任意 | 广播未启动 | 执行失败 |
| 任意 | 执行成功时 | 发送广播 |

## 返回值

| 命令 | 条件 | 返回值 |
| - | - | - |
| 任意 | 失败时 | -1 |
| 任意 | 成功时 | 0 |
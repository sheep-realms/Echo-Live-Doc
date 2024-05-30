# next

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.4.0</span>
</span>
<span class="feature-tag" title="限制条件" markdown>
    <span class="icon">:material-broadcast:</span>
    <span class="text">仅限广播模式</span>
</span>

发送 [`echo_next`](../broadcast/api/echo_next.md) 广播，打印下一条消息。

## 语法

`next [<目标>]`

## 参数

- `<目标>`
    - 目标客户端的 UUID 或识别名。

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
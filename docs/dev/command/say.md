# say

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.4.0</span>
</span>

在日志中输出一段消息。

## 语法

`say <消息>`

## 参数

- `<消息>`
    - 任意消息文本。

## 效果

| 命令 | 触发条件 | 结果 |
| - | - | - |
| 任意 | 参数未正确指定 | 无法解析 |
| 任意 | 执行成功时 | 在日志中输出消息 |

## 返回值

| 命令 | 条件 | 返回值 |
| - | - | - |
| 任意 | 无法解析时 | -1 |
| 任意 | 成功时 | 0 |
# theme

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.4.0</span>
</span>
<span class="feature-tag" title="限制条件" markdown>
    <span class="icon">:material-broadcast:</span>
    <span class="text">仅限广播模式</span>
</span>

发送 [`set_theme`](../broadcast/api/set_theme.md) 广播，更改客户端主题。

## 语法

`theme <主题名称> [<目标>]`

## 参数

- `<主题名称>`
    - 主题 ID，见[主题列表](../../custom/theme.md)。
- `<目标>`
    - 目标客户端的 UUID 或识别名。

## 效果

| 命令 | 触发条件 | 结果 |
| - | - | - |
| 任意 | 参数未正确指定 | 无法解析 |
| 任意 | 广播未启动 | 执行失败 |
| 任意 | 执行成功时 | 发送广播 |

## 返回值

| 命令 | 条件 | 返回值 |
| - | - | - |
| 任意 | 无法解析时 | -1 |
| 任意 | 失败时 | -1 |
| 任意 | 成功时 | 0 |
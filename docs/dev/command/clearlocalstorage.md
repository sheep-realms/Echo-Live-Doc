# clearlocalstorage

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.4.7</span>
</span>
<span class="feature-tag" title="限制条件" markdown>
    <span class="icon">:material-console-line:</span>
    <span class="text">函数中不可用</span>
</span>

清空本地存储数据，需要弹出对话框确认。

## 语法

`clearlocalstorage`

## 参数

此命令不需要任何参数。

## 效果

| 命令 | 触发条件 | 结果 |
| - | - | - |
| 任意 | 在函数中执行 | 执行失败 |
| 任意 | 执行成功时 | 弹出确认对话框 |

## 返回值

| 命令 | 条件 | 返回值 |
| - | - | - |
| 任意 | 失败时 | -1 |
| 任意 | 成功时 | 0 |
# getlang

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.4.7</span>
</span>

获取当前所使用的本地化信息。

## 语法

`getlang [(code|ietf|name)]`

## 参数

- `(code|ietf|name)`
    - 若忽略此参数则默认选择 `code`。
    - `code`：获取语言的 ISO 639-3 代码。
    - `ietf`：获取语言的 IETF 代码。
    - `name`：获取语言的本地化名称。

## 效果

| 命令 | 触发条件 | 结果 |
| - | - | - |
| 任意 | 执行成功时 | 获取本地化信息 |

## 返回值

| 命令 | 条件 | 返回值 |
| - | - | - |
| 任意 | 成功时 | 获取到的本地化信息 |
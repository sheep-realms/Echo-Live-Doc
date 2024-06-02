# var

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.4.0</span>
</span>

设置变量，可在命令中通过 `@<变量名>` 使用。

## 语法

- `var <变量名> ...`
    - `... [<运算符>] [<值>]`
    - `... (++|--)`
    - `... (get|del)`
    - `... return <子命令>`

## 参数

- `<变量名>`
    - 仅限使用大小写英文字母、数字和下划线，且首个字符不能是数字，长度在 1 ~ 64 之间（包含）。
- `<运算符>`
    - 可以是以下值：

| 值 | 描述 |
| - | - |
| `=` | 赋值 |
| `+` | 加法 |
| `-` | 减法 |
| `*` | 乘法 |
| `/` | 除法 |
| `/^` | 向上整除 |
| `/_` | 向下整除 |
| `//` | 四舍五入整除 |
| `%` | 求余 |
| `^^` | 幂 |
| `&+` | 字符串拼接 |
| `^` | 按位异或 |
| `|` | 按位或 |
| `&` | 按位与 |
| `<<` | 零填充左位移 |
| `>>` | 有符号右位移 |
| `>>>` | 零填充右位移 |
| `max` | 最大值 |
| `min` | 最小值 |
| `typeof` | 类型查询 |

- `<值>`
    - 需要用于计算的值。
    - 例如 `var a - 2` 这条命令表示用 `2` 减去 `a` 的值，并将结果赋值给 `a`。
- `++|--`
    - 自增或自减运算。
- `get`
    - 获取变量的值。
- `del`
    - 删除变量。
- `return`
    - 从命令的返回值中获取值赋值给变量。
- `<子命令>` 
    - 任意命令。

## 效果

| 命令 | 触发条件 | 结果 |
| - | - | - |
| 任意 | 参数未正确指定 | 无法解析 |
| 除<br>`var <变量名>`、<br>`var <变量名> = ...`、<br>`var <变量名> return ...`<br>之外 | 变量未声明 | 执行失败 |
| 任意 | 执行成功时 | 声明、设置或删除变量。详见下： |

若成功：

- `var <变量名>` 或 `var <变量名> =`
    - 设置变量值为 `undefined`。
- `var <变量名> <运算符> <值>` 或  `var <变量名> return <子命令>`
    - 设置变量计算后的值。
- `var <变量名> ++|--`
    - 设置变量自增或自减后的值。
- `var <变量名> get`
    - 获取变量的值。
- `var <变量名> del`
    - 删除变量。

## 返回值

| 命令 | 条件 | 返回值 |
| - | - | - |
| 任意 | 无法解析时 | -1 |
| 任意 | 失败时 | -1 |
| `var <变量名>`、<br>`var <变量名> = ...`、<br>`var <变量名> return ...`、<br>`var <变量名> get|del` | 成功时 | 0 |
| 任意 | 成功时 | 所设置变量的值 |
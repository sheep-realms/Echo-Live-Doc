# EchoLiveHookUnit

`EchoLiveHookUnit` 是 Hook 单位的实例化类型，用于管理 Hook 单位。

## 实例属性

| 属性名 | 默认值 | 描述 |
| - | - | - |
| `id` | 无 | Hook ID。 |
| `name` | 无 | 事件名称。 |

### 只读属性

| 属性名 | 描述 |
| - | - |
| `parent` | 父级对象，即 [`EchoLiveHook`](EchoLiveHook.md)，恒为 `echoLiveSystem.hook`。 |
| `index` | Hook 索引编号。 |
| `indexByName` | Hook 在事件中的索引编号。 |

## 构造函数

语法：

``` js
new EchoLiveHookUnit(id, name)
```

| 参数 | 预期类型 | 默认值 | 描述 |
| - | - | - | - |
| `id` | `Number` | 无 | Hook ID。 |
| `name` | `String` | 无 | 事件名称。 |

## 实例方法

### `remove()`

移除 Hook。

语法：

``` js
remove()
```
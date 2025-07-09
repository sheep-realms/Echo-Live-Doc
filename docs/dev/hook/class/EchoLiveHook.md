# EchoLiveHook

`EchoLiveHook` 是 Echo-Live 的 Hook 管理器，可以通过实例 `echoLiveSystem.hook` 访问到它。

## 实例属性

| 属性名 | 默认值 | 描述 |
| - | - | - |
| `hooks` | `[]` | Hook 列表。 |
| `lastHookID` | `-1` | 最后一个 Hook 的 ID。 |
| `debug` | | 调试功能。 |
| `debug.log_trigger` | `false` | Hook 触发时在控制台中输出。 |

## 实例方法

### `create()`

创建一个 Hook。

语法：

``` js
create(name, method)
```

| 参数 | 预期类型 | 默认值 | 描述 |
| - | - | - | - |
| `name` | `String` | 无 | 事件名称。 |
| `method` | `Function` | `() => {}` | Hook 触发时调用的方法。 |

返回一个 [`EchoLiveHookUnit`](EchoLiveHookUnit.md) 实例。

### `find()`

查找 Hook。

语法：

``` js
find(id)
```

| 参数 | 预期类型 | 默认值 | 描述 |
| - | - | - | - |
| `id` | `Number` | 无 | Hook ID。 |

如果找到，则返回 Hook 在 `EchoLiveHook.hooks` 中的数据，否则返回 `undefined`。

### `findIndex()`

查找 Hook 索引编号。

语法：

``` js
findIndex(id)
```

| 参数 | 预期类型 | 默认值 | 描述 |
| - | - | - | - |
| `id` | `Number` | 无 | Hook ID。 |

如果找到，则返回 Hook 索引编号，否则返回 `-1`。

### `findIndexByName()`

查找 Hook 在事件中的索引编号。

语法：

``` js
findIndexByName(name, id)
```

| 参数 | 预期类型 | 默认值 | 描述 |
| - | - | - | - |
| `name` | `String` | 无 | 事件名称。 |
| `id` | `Number` | 无 | Hook ID。 |

如果找到，则返回 Hook 在事件中的索引编号，否则返回 `-1`。

### `filter()`

以事件名称过滤 Hook。

语法：

``` js
filter(name)
```

| 参数 | 预期类型 | 默认值 | 描述 |
| - | - | - | - |
| `name` | `String` | 无 | 事件名称。 |

如果找到，则返回 Hook 在 `EchoLiveHook.hooks` 中的数据，否则返回 `undefined`。

### `remove()`

移除 Hook。

语法：

``` js
remove(id)
```

| 参数 | 预期类型 | 默认值 | 描述 |
| - | - | - | - |
| `id` | `Number` | 无 | Hook ID。 |

### `clear()`

清空 Hook。

语法：

``` js
clear(name)
```

| 参数 | 预期类型 | 默认值 | 描述 |
| - | - | - | - |
| `name` | `String|undefined` | 无 | 事件名称。 |

如果未指定 `name`，将会移除所有 Hook，否则只移除指定事件的 Hook。

### `trigger()`

触发 Hook。

语法：

``` js
trigger(name, data)
```

| 参数 | 预期类型 | 默认值 | 描述 |
| - | - | - | - |
| `name` | `String` | 无 | 事件名称。 |
| `data` | 任意 | 无 | 触发 Hook 时需要传递的数据。 |
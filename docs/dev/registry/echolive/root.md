# echolive:root

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.5.0</span>
</span>

根注册表，为当前命名空间中的所有注册表提供默认值。

## :material-list-box-outline: 属性

| 属性 ||
| - | - |
| 唯一键 | `name` |
| 继承 | 无 |

## :material-code-json: 默认值

该注册表未指定默认值。

## :material-code-json: 预期值

该注册表预期写入 Object 类型的数据，包含以下内容：

| 键名 | 描述 |
| - | - |
| `name` | 注册表名，包含命名空间，没有命名空间将使用 `echolive` 作为命名空间。 |
| `unique_key` | 注册表的唯一键名。 |
| `default_data` | 注册表项的默认值。 |
| `inherit` | 继承的注册表名。填写此值将会忽略 `default_data` 并从指定的注册表继承默认值。 |
| `sync` | 是否为同步注册表。 |
| `is_function` | 是否为函数注册表。此值为 `true` 时 `sync` 字段将失效。 |
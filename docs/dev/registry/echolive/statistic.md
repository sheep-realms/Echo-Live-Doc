# echolive:statistic

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.7.0</span>
</span>

注册统计项。

## :material-list-box-outline: 属性

| 属性 ||
| - | - |
| 唯一键 | `name` |
| 继承 | 无 |

## :material-code-json: 默认值

``` js
{
    name: 'statistic',
    unique_key: 'name',
    sync: true,
    default_data: {
        name: undefined,
        type: 'number',
        default: 0,
        unit: undefined,
        source: 'custom'
    }
}
```

## :material-code-json: 预期值

### `name`

统计项名称。

### `type`

数据类型，可选值为：

- `number`：数字，默认值。
- `timestamp`：时间戳。

### `default`

初始值，默认为 `0`。

### `unit`

业务单位，从本地化键 `unit.*` 中读取。

### `source`

数据来源，可选值为：

- `custom`：自定义，默认值。通过在程序中埋点来统计数据。
- `daily_increment`：每个活动日自增。
- `method`：通过注册方法来获取数据。以此注册的统计项不会被保存，仅在导出时生成。

### `reference`

参考值，指定统计项键名。

仅在 `source` 为 `daily_increment` 时有效，用于通过上次会话时间计算新的统计周期是否已经开始。参考值的数据来源不能是 `method`。此类统计项并不会自动更新参考值的时间戳。
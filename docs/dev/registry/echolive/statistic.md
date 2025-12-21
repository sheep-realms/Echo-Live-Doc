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
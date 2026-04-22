# echolive:sound

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.5.0</span>
</span>

注册音效。

## :material-list-box-outline: 属性

| 属性 ||
| - | - |
| 唯一键 | `name` |
| 继承 | 无 |

## :material-code-json: 默认值

``` js
{
    title: undefined,
    name: undefined,
    path: undefined,
    type: 'print',
    safe_duration: 0,
    pick_strategy: 'random',
    allow_duplicate: false
}
```

## :material-history: 历史

| 版本 | 描述 |
| - | - |
| 1.5.0 | 加入了 `echolive:sound` 注册表。 |
| 1.5.5 | 新增 `type` 字段，默认值为 `"print"`。<br>新增 `allow_duplicate` 字段，默认值为 `false`。 |
| 1.7.5 | 新增 `safe_duration` 字段，默认值为 `0`。<br>新增 `pick_strategy` 字段，默认值为 `"random"`。<br>新增 `oscillator` 字段，默认未定义，包含字段 `volume_multiplier` 和 `rate_multiplier`。 |
| 1.8.0 | 新增 `title` 字段，用于注册音效名称，支持文本翻译组件。如无此字段则会通过 `name` 字段生成本地化键。 |
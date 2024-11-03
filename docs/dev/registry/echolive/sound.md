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
    name: undefined,
    path: undefined,
    type: 'print',
    allow_duplicate: false
}
```

## :material-history: 历史

| 版本 | 描述 |
| - | - |
| 1.5.0 | 加入了 `echolive:sound` 注册表。 |
| 1.5.5 | 新增 `type` 字段，默认值为 `"print"`。<br>新增 `allow_duplicate` 字段，默认值为 `false`。 |
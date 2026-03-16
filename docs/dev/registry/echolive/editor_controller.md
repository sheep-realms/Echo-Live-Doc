# echolive:editor_controller

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.7.4</span>
</span>

注册编辑器中的控制栏及其快捷键。

## :material-list-box-outline: 属性

| 属性 ||
| - | - |
| 唯一键 | `name` |
| 继承 | 无 |

## :material-code-json: 默认值

``` js
{
    name: undefined,
    type: 'item',
    title: 'missingno',
    icon: undefined,
    shortcut: {},
    action: {
        type: 'none',
        value: undefined
    }
}
```

## :material-code-json: 预期值

### `name`

控制器名称，用于绑定行为。

### `type`

控制器类型，可选值为：

- `item`：普通控制器，默认值。
- `hidden`：不可见控制器。

### `title`

控制器标题，用于其显示名称，支持使用[本地化文本组件](../../../reference/text-component.md)。

### `icon`

控制器图标名称，用于在控制栏中显示的图标，可选值为 [`icon`](icon.md) 注册表中的项目。

### `shortcut`

激活控制器可用的快捷键，包含以下字段：

- `keys`：按键名称（基于 `KeyboardEvent.code`），支持组合键。该字段中应忽略 `Ctrl`，因为无论如何该按键都会被要求按下。示例如下：
    - `ArrowUp` 表示 <kbd>Ctrl</kbd> + <kbd>↑</kbd>；
    - `Shift+KeyS` 表示 <kbd>Ctrl</kbd> + <kbd>⇧ Shift</kbd> + <kbd>S</kbd>。
- `description`：快捷键描述，用于在控制器鼠标悬停提示中提示快捷键。

### `action`

控制器触发后的行为，包含以下字段：

- `type`：行为名称，可以是以下值：
    - `insert_text_at_cursor`：在光标处插入文本。
    - `show_popups`：显示悬浮窗。
    - `none`：什么也不做。
- `value`：行为参数。
    - 当 `type` 值为 `insert_text_at_cursor` 时，有以下字段：
        - `before`：在光标前插入的内容。
        - `after`：在光标后插入的内容。
        - `forceInputAfter`：布尔值，未选中文本时强制在光标后插入内容，默认为 `false`。
        - `forceRepeatBefore`：布尔值，当光标前有相同内容时强制插入内容，默认为 `false`。
        - `forceRepeatAfter`：布尔值，当光标后有相同内容时强制插入内容，默认为 `false`。
        - `firstClear`：布尔值，当（起始）光标位于文本框起始位置时不在光标前插入内容，默认为 `false`。
        - `selectedTextFilter`：选中文本过滤器，指定位于注册表 `editor_controller_method` 中的函数名称。
        - `setFocus`：布尔值，是否设置焦点，默认为 `true`。
    - 当 `type` 值为 `show_popups` 时，有以下字段：
        - `id`：悬浮窗的 ID。
        - `focus`：显示悬浮窗后需要聚焦的元素选择器字符串。

## :material-lightbulb-on: 你知道吗

- 此注册表中定义了一个名为 `disabled_save` 的不可见控制器，其行为是什么也不做，以此来阻止按下 <kbd>Ctrl</kbd> + <kbd>S</kbd> 时的浏览器默认行为。
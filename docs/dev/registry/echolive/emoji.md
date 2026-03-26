# echolive:emoji

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.5.0</span>
</span>

注册表情包，以供编辑器和对话框使用。

## :material-list-box-outline: 属性

| 属性 ||
| - | - |
| 唯一键 | `meta.name` |
| 继承 | 无 |

## :material-code-json: 默认值

该注册表有再注册过程，实际默认值取决于再注册过程。

``` js
{}
```

## :material-code-json: 预期值

### 元数据

表情包的元数据存储于 `meta` 字段中。

#### `name`

表情包名称，建议使用命名空间以防命名冲突。

#### `namespace`

短命名空间，用于在编辑器中调用。若短命名空间冲突，将使用 `name` 字段作为命名空间。

#### `title`

表情包标题，用于其显示名称，支持使用[本地化文本组件](../../../reference/text-component.md)。

#### `author`

作者信息，支持使用[参考元数据组件](../../../reference/reference-component.md)。

#### `license`

授权协议，支持使用[参考元数据组件](../../../reference/reference-component.md)。

### 地址前缀

为避免重复填写地址数据，可复用的地址片段存储于 `path` 字段中。

#### `translate`

翻译键名前缀，请注意末尾的 `.` 需手动填写。

#### `images`

图片路径前缀，请注意末尾的 `/` 需手动填写。

### 图片样式

图片样式信息存储于 `image` 字段中。

#### `margin`

图片外边距，包含以下字段：

- `start`：逻辑行首外边距。
- `end`：逻辑行末外边距。
- :material-delete:{.text-light} `left`：左外边距，仅为兼容而保留，不建议使用。
- :material-delete:{.text-light} `right`：右外边距，仅为兼容而保留，不建议使用。

以上字段默认值均为 `unset`。

#### `rendering`

图片重采样方式，可以是以下值：

- `auto`：默认采样方式。
- `pixelated`：最近邻（硬边缘）采样。

#### `review_size`

图片在编辑器中的预览尺寸，可以是以下值：

- `small`：最小。
- `middle`：适中，未填写等效于此值。
- `large`：最大。

#### `size`

图片在对话框中的尺寸，包含 `width` 和 `height` 字段，这两个字段包含以下字段：

- `value`：目标尺寸。
- `max`：最大尺寸。
- `min`：最小尺寸。

以上字段包含 CSS 长度单位。

#### `is_emoji`

是否为文字表情。

#### `show_title`

是否在编辑器中鼠标悬停时显示标题，布尔值，默认为 `true`。搭配 `is_emoji` 使用可禁用文字表情的悬停提示标题。

### 内容

表情包内容存储于 `content` 字段中，类型为数组。

数组中的每一个元素都有一个 `type` 字段，可以是以下值：

- `emoji`：表情，默认值。
- `group`：分组标题。

#### `emoji` 类型

当 `type` 字段为 `emoji` 时，有以下字段：

- `name`：表情名称。
- `title`：表情标题，用于其显示名称，支持使用[本地化文本组件](../../../reference/text-component.md)，本地化键名前缀为 `emoji.<path.translate>emoji.`。
- `path`：图片路径。

#### `group` 类型

当 `type` 字段为 `group` 时，有以下字段：

- `title`：分组标题，用于其显示名称，支持使用[本地化文本组件](../../../reference/text-component.md)，本地化键名前缀为 `emoji.<path.translate>group.`。

## :material-history: 历史

| 版本 | 描述 |
| - | - |
| 1.5.0 | 加入了 `echolive:emoji` 注册表。 |
| 1.7.7 | `image.margin` 新增字段 `start` 和 `end`，用于表示逻辑行方向。<br>`left` 和 `right` 字段默认值由 `0.5em` 改为 `unset`。<br>`left` 和 `right` 字段出于兼容考虑仍然保留，但不建议使用。 |
| 1.7.8 | `image.isEmoji` 更名为 `image.is_emoji`。 |
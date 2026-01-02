# 注册表

注册表是 Echo-Live 集中管理数据的一项机制。

## :material-cog: 机制

### 注册表名

注册表的名称包含命名空间，使用冒号 `:` 分隔命名空间与名称，如未指定命名空间将会自动指定命名空间为 `echolive`。

### 键值

注册表中的每一个项目都有一个在当前表中唯一的键名，如果对同一个键值重复写入，将会触发覆写机制。此外，一些注册表含有隐性默认值，对这些注册表的键值初次写入也会触发覆写机制。

值的类型必须可被转换为 JSON，否则会被忽略。

如果值包含循环引用将会引发错误。

### 值的覆写

原始值与写入值类型类型不同时，将会直接覆盖。

当原始值与写入值类型相同时：

- 如果类型为 Object，写入值将会与原始值深度合并，其中嵌套的值也遵循覆写规则；
- 如果类型为 Array，写入值将会添加至原始值末尾；
- 其他类型则直接覆盖。

### 特殊注册表

一些注册表具有特殊功能：

#### `root`

这是整个命名空间的根注册表，该注册表可以为当前命名空间中的所有注册表提供默认值。

例如有一个 `example:test` 注册表，它在设置值时会尝试从 `example:root` 读取默认值。

如果 `example:root` 中的注册表数据指定了继承的注册表（即填写了 `inherit` 字段），则会尝试读取被继承的注册表的默认值，后续的继承以此类推。

### 函数注册表

在 `root` 注册表中定义注册表时，将字段 `is_function` 值设为 `true` 可创建函数注册表。这种情况下，字段 `sync` 将会失效。

函数注册表只能用于存储函数数据，常规注册表无法储存函数数据。

## :material-sign-direction: 运行流程

注册表的运行流程分为以下几个阶段：

1. 实例化 —— `EchoLiveRegistry` 类实例化，创建 `echolive:root` 注册表。
2. 初始化 —— 导入 `echolive:root` 注册表，创建固有注册表，完成初始化。
3. 导入注册表 —— 导入其余注册表数据。
4. 再注册 —— 载入业务逻辑，可能会对注册表数据进行修改并再次写入。

## :material-format-list-bulleted-square: 注册表列表 { id="registry-list" }

| 注册表名 | 存储路径 | 作用 |
| - | - | - |
| [`echolive:root`](registry/echolive/root.md) | `res/data/root.js` | 注册表实例创建时创建的第一个注册表，用于在初始化阶段创建其他注册表，并为注册表值提供默认值。 |
| [`echolive:avatar`](registry/echolive/avatar.md) | `res/data/avatar.js` | 虚拟形象，用于形象播放器。 |
| [`echolive:border_style`](registry/echolive/border_style.md) | `res/data/border_style.js` | CSS 中所有边框样式，为[配置文件编辑器](../custom/config.md#config-editor)提供候选值。 |
| [`echolive:emoji`](registry/echolive/emoji.md) | `res/data/emoji.js` | 编辑器中的表情包。 |
| [`echolive:emoji_namespace`](registry/echolive/emoji_namespace.md) | 无 | 表情包命名空间的重定向表，在编辑器中加载表情包时自动写入。 |
| [`echolive:language`](registry/echolive/language.md) | `lang/*.js` | 本地化数据，一般情况下最多只有源语言和配置选择的语言。 |
| [`echolive:language_index`](registry/echolive/language_index.md) | `lang/index.js` | 本地化索引表，包含所有可用的本地化数据的基本信息。 |
| [`echolive:live_controller`](registry/echolive/live_controller.md) | `res/data/live_controller.js` | 对话框的控制栏。 |
| [`echolive:live_theme`](registry/echolive/live_theme.md) | `res/data/live_theme.js` | 前台页面主题信息。 |
| [`echolive:message_filter`](registry/echolive/message_filter.md) | `res/data/message_filter.js` | 对话框消息过滤器。 |
| [`echolive:palette`](registry/echolive/palette.md) | `res/data/palette.js` | 编辑器中的调色板。 |
| [`echolive:print_effect`](registry/echolive/print_effect.md) | `res/data/print_effect.js` | 字符打印动效。 |
| [`echolive:script`](registry/echolive/script.md) | 无 | 未使用，计划用于加载脚本。 |
| [`echolive:settings_data`](registry/echolive/settings_data.md) | `res/data/settings_about_link.js`、<br>`res/data/settings_navigation.js` | 配置文件编辑器的菜单、关于页面链接等数据，仅使用特定的注册表键。 |
| [`echolive:sound`](registry/echolive/sound.md) | `res/data/sound.js` | 音效信息。 |
| [`echolive:statistic`](registry/echolive/statistic.md) | `res/data/statistic.js` | 统计项。 |
| [`echolive:statistic_method`](registry/echolive/statistic_method.md) | `res/data/statistic_method.js` | 统计项方法。 |
| [`echolive:stylesheet`](registry/echolive/stylesheet.md) | 无 | 未使用，计划用于加载样式表。 |
| [`echolive:system`](registry/echolive/system.md) | 无 | 与注册表相关的系统信息，仅使用特定的注册表键。 |
| [`echolive:text_style`](registry/echolive/text_style.md) | `res/data/text_style.js` | [消息格式](../message/style.md)中的样式字段。 |
| [`echolive:timing_function`](registry/echolive/timing_function.md) | `res/data/timing_function.js` | 动效时间曲线。 |
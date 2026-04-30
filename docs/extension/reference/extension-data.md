# 扩展数据格式

**扩展数据格式**是注册扩展时所输入的数据格式。

## 结构

- `meta`：扩展元数据。
    - `title`：扩展标题，支持[本地化文本组件](../../reference/text-component.md)，本地化键前缀为 `extension.<扩展名称>.`。
    - `name`：扩展识别名，应与扩展文件夹名称一致。
    - `schema_version`：扩展所使用的注册数据格式版本，由 3 个数字组成的数组，每个数字的含义依次为：
        - 主版本号：恒为 2。扩展主版本号与内置主版本号不一致将无法载入。
        - 次版本号：当扩展注册数据发生更名、移动等可能产生兼容问题的更改时，次版本号 +1，修订版本重置为 0。扩展次版本号低于内置次版本号时，可能需要转换或无法载入。扩展次版本号高于内置次版本号时将无法载入。
        - 修订版本号：当扩展注册数据发生新增等小型修改且不会产生兼容问题的更改时，修订版本 +1。当前为 1。无论如何都不会影响扩展载入。
    - `extension_version`：扩展自身版本号，格式为字符串。
    - `icon`：扩展图标，从注册表 [`echolive:icon`](../../dev/registry/echolive/icon.md) 中取值，默认为 `material:puzzle`。
    - `cover`：扩展封面图像地址，以扩展自身文件夹为起点。设置扩展封面将会覆盖扩展图标。
    - `description`：扩展描述，支持[本地化文本组件](../../reference/text-component.md)，本地化键前缀为 `extension.<扩展名称>.`。
    - `project_url`：扩展的项目 URL 地址。
    - `author`：作者，支持[参考元数据组件](../../reference/reference-component.md)，本地化键前缀为 `extension.<扩展名称>.`。
    - `license`：授权协议，支持[参考元数据组件](../../reference/reference-component.md)，本地化键前缀为 `extension.<扩展名称>.`。
- `register_hook`：[注册器 Hook](../reference/register-hook.md)。
- `localization_patch`：本地化补丁，格式为 Object。键名为 ISO 639-3 语言代码，值为本地化键值对。

## 版本
| 扩展数据格式版本 | Echo-Live 版本 |
| - | - |
| `2.0.2` | [`1.8.2`](https://github.com/sheep-realms/Echo-Live/releases/tag/1.8.2){ target="_blank" } |
| `2.0.1` | [`1.8.1`](https://github.com/sheep-realms/Echo-Live/releases/tag/1.8.1){ target="_blank" } |
| 无 | [`1.8.0`](https://github.com/sheep-realms/Echo-Live/releases/tag/1.8.0){ target="_blank" } |
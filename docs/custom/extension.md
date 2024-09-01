# 扩展

!!! warning "扩展已暂停支持"

    由于扩展系统正在重构，自 1.5.0 版本开始扩展系统暂时停用。

    由于 1.5.0 版本以新机制[注册表](../dev/registry.md)取代了原有的数据加载逻辑，将数据层与业务逻辑层解耦，扩展系统已不再正常工作。但是，我们即将可以通过注册表为扩展提供更丰富的定制选择。

    如果您对扩展系统有什么建议，欢迎提出。

Echo-Live 支持扩展，可用于增加额外资源。

**注意：Echo-Live 的扩展仅作规范导入分享资源之用，虽然目前仅支持增加额外音频资源和主题，但实际上可以被用来做任何事，因此请不要安装来路不明的扩展。**

## :material-import: 安装
1. 将扩展（是一个文件夹）放入 `extensions` 文件夹。
2. 在 `extensions.js` 中插入该扩展的文件夹名称。

## :material-code-tags: 开发
首先，您需要为您的扩展创建一个文件夹，推荐使用英文字符命名。在该文件夹中创建文件 `pack.js`，使用 `extensionManager.load()` 方法加载扩展资源。

该方法需要传入 Object 数据，示例如下：
``` javascript linenums="1"
extensionManager.load({
    meta: {
        namespace: 'example'
    },
    addon: {
        audio: [
            {
                name: 'sonar',
                path: 'audio/sonar.ogg'
            }
        ],
        theme: [
            {
                name: 'example_theme',
                title: '示例主题',
                description: '主题描述',
                style: 'style/example.css',
                script: [
                    'script/example.js'
                ]
            }
        ]
    }
});
```

| 键名 | 类型 | 描述 |
| - | - | - |
| `meta` | Object | 扩展元数据。 |
| `meta.namespace` | String | 命名空间，与文件夹名称一致。 |
| `addon` | Object | 扩展所添加的额外内容。 |
| `addon.audio` | Array | 音效列表。 |
| `addon.audio[].name` | String | 音效 ID。 |
| `addon.audio[].path` | String | 音效路径，以 `pack.js` 所在文件夹为起点。 |
| `addon.theme` | Array | 主题列表。 |
| `addon.theme[].name` | String | 主题 ID。 |
| `addon.theme[].title` | String | 主题名称。 |
| `addon.theme[].description` | String | 主题描述。 |
| `addon.theme[].style` | String | 主题样式表路径，以 `pack.js` 所在文件夹为起点。请通过 @import 导入更多样式表。 |
| `addon.theme[].script` | Array | 主题脚本路径，以 `pack.js` 所在文件夹为起点。 |

使用扩展添加新音效后，需要以 `命名空间:音效ID` 的格式调用音效，主题同理。

### :material-script-text: 主题脚本

主题脚本尚处于测试阶段，未来有可能发生更改，请不要过度依赖主题脚本。
# 快速开始

要制作扩展，首先需要了解一个重要概念 —— [注册表](../dev/registry.md)。这是集中管理数据的一项机制，扩展基于注册表运作。

我们可以通过制作一个简单的扩展来了解这项机制。

## 创建扩展

为了便于调试，我们可以直接在 Echo-Live 的 `extensions` 文件夹中创建一个**扩展文件夹**。我们就给这个文件夹命名为 `john_smith` 吧！

扩展还需要一个**入口文件**，我们还需要在扩展文件夹中创建一个 `main.js` 文件。

至此，我们完成了一个扩展的创建。当然，这个扩展现在还没有任何内容。


## 扩展注册

在让扩展开始做点什么之前，我们得先让它注册自己，不然我们的扩展管理器永远不会知道它到底有没有正常运作。

这里我们要用到 `extensionManager.load()` 方法，这是扩展管理器加载扩展的方法。我们需要在 `main.js` 中写入以下内容：

``` javascript title="main.js" linenums="1"
extensionManager.load({
    meta: {
        // 扩展标题
        title: "John Smith",
        // 扩展识别名，应与文件夹名称一致
        name: "john_smith",
        // 扩展所使用的注册数据格式版本
        // 请注意查看参考列表中扩展数据格式版本与 Echo-Live 版本的对应关系
        schema_version: [2, 0, 1],
        // 扩展自身版本号
        extension_version: "1.0.0",
        // 描述
        description: "这里是扩展描述。"
    }
});
```

这样，扩展便完成了注册..... 吗？

稍等一下，我们还差最重要的一步，那就是在扩展列表中加入这个扩展。

打开 Echo-Live 的 `extensions.js` 文件，在里面加入这个扩展的名字，就像这样：

``` javascript title="main.js" linenums="1"
const extensions = [
    "john_smith"
];
```

现在，打开[配置文件编辑器](../custom/config.md#config-editor)（如果您已经打开了的话，请刷新），导航到 “编辑” 标签页，选择 “扩展管理器” 项目。不出意外的话，您可以在这里看到刚刚创建的扩展了。


## 注册新数据

目前我们创建的扩展仅仅只是创建了自身，除此之外什么也没做。

现在，是时候该做点什么了。就从比较简单的 [`echolive:border_style`](../dev/registry/echolive/border_style.md) 这个注册表下手吧！这是一个为配置文件编辑器提供边框样式选项的注册表。

Echo-Live 中其实准备了一些开发者工具，您可以在 `dev` 文件夹中找到 `registry.html`，这是注册表查看器。您可以使用注册表查看器来了解注册表中都有什么内容。

我们可以看到，`echolive:border_style` 注册表中 `solid` 项目的内容是这样的：

``` json
{
    "value": "solid",
    "name": "solid"
}
```

以此为模板，我们来添加一种名为 `john_smith` 的边框样式吧！虽然不会有什么效果。

要注册数据，需要用到[注册器 Hook](reference/register-hook.md) 字段 `register_hook`，我们就把它放在 `meta` 字段的下方吧：

``` javascript title="main.js" linenums="1" hl_lines="9"
extensionManager.load({
    meta: {
        title: "John Smith",
        name: "john_smith",
        schema_version: [2, 0, 1],
        extension_version: "1.0.0",
        description: "这里是扩展描述。"
    }, // <-- 注意别漏了逗号！
    register_hook: {}
});
```

注册器 Hook 有不同的载入时机，但目前我们不用考虑那么多底层实现，直接用 `loaded`：

``` javascript title="main.js" linenums="1" hl_lines="10"
extensionManager.load({
    meta: {
        title: "John Smith",
        name: "john_smith",
        schema_version: [2, 0, 1],
        extension_version: "1.0.0",
        description: "这里是扩展描述。"
    },
    register_hook: {
        loaded: []
    }
});
```

Hook 字段是一个数组，这意味着我们可以在其中同时插入多个注册表的数据。

我们要对 `echolive:border_style` 注册表写入新数据，就在这里点名：

``` javascript title="main.js" linenums="1" hl_lines="11 12 13 14"
extensionManager.load({
    meta: {
        title: "John Smith",
        name: "john_smith",
        schema_version: [2, 0, 1],
        extension_version: "1.0.0",
        description: "这里是扩展描述。"
    },
    register_hook: {
        loaded: [
            {
                registry: "echolive:border_style"，
                value: {}
            }
        ]
    }
});
```

然后，为它添加 `john_smith` 这个新的边框样式：

``` javascript title="main.js" linenums="1" hl_lines="14 15"
extensionManager.load({
    meta: {
        title: "John Smith",
        name: "john_smith",
        schema_version: [2, 0, 1],
        extension_version: "1.0.0",
        description: "这里是扩展描述。"
    },
    register_hook: {
        loaded: [
            {
                registry: "echolive:border_style"，
                value: {
                    name: "john_smith",
                    value: "john_smith"
                }
            }
        ]
    }
});
```

至此，我们已经完成了一个简单的扩展。保存好你的扩展，去注册表查看器看看你的成果吧！


（未完待续）
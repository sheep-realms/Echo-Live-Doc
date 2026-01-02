# API 参数格式
Echo-Live 的广播数据是一种 Object 类型的数据，内容如下：

| 键名 | 类型 | 预期值 | 描述 |
| - | - | - | - |
| `action` | String | 动作名称 | 见本文档目录中的广播 API 文档。 |
| `target` | String 或 Array&lt;Srting&gt; | undefined、UUID 或识别名 | 可选，指定接收方 UUID 或识别名，设为 undefined 即全体接收。 |
| `from` | Object | 发送来源 | 见下文。 |
| `data` | Object | | 需要传递的数据。 |

## target 参数

`target` 存在如下几种格式：

- UUID，例如：`2c3103f0-b4ec-4041-b17a-a3d5d19d515a`；
- 识别名，以 `@` 开头。
    - `@__` 开头的识别名为保留识别名，可以指定终端类型：
        - `@__ws_server` —— WebSocket 服务器；
        - `@__server` —— 所有服务器；
        - `@__client` —— 所有类型的客户端；
        - `@__终端类型` —— 指定类型的所有终端，见下文。
    - 仅 `@` 开头的识别名将指定设定了对应的自定义名称的终端，如 `@example` 即指定自定义名称为 `example` 的终端。

当以 `-` 开头时，视为反选目标。

当 `target` 是数组时，数组中的每一个字符串都可以指定一个目标，数组中的 `undefined` 和 `null` 会被忽略。

## from 参数

`from` 参数是一个 Object 对象，有以下参数：

| 键名 | 类型 | 预期值 | 描述 |
| - | - | - | - |
| `name` | String | 识别名 | 终端的自定义识别名。如果没有自定义识别名则为 UUID。 |
| `uuid` | String | UUID | 终端的 UUID。 |
| `type` | String | 发送者类型 | 见下文。 |
| `timestamp` | Number | 时间戳 | 消息发送时的时间戳。 |
| `expand` | Object | 对象 | 额外元数据，可能不存在。目前尚无实际作用。 |

### from 中的 type 参数
`type` 参数可以是以下值：

| 值 | 描述 |
| - | - |
| `unknown` | 未知。此类型仅用于确保继承结构完整性，正常情况下不应出现。 |
| `server` | 服务端。例如编辑器。 |
| `client` | 客户端。此类型仅用于确保继承结构完整性，正常情况下不应出现。 |
| `live` | 对话框。 |
| `history` | 历史记录浏览器。 |

``` javascript title="示例"
{
    action: 'close',
    target: undefined,
    from: {
        name: '@example',
        uuid: '2c3103f0-b4ec-4041-b17a-a3d5d19d515a',
        type: 'live',
        timestamp: 1721491200000
    },
    data: {}
}
```

## :material-history: 历史

| 版本 | 描述 |
| - | - |
| 1.5.5 | `target` 参数现在可以是 Array 类型以选择多个目标。<br>`target` 参数新增反选符号 `-`。 |
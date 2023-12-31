# API 参数格式
Echo-Live 的广播数据是一种 Object 类型的数据，内容如下：

| 键名 | 类型 | 预期值 | 描述 |
| - | - | - | - |
| `action` | String | 动作名称 | 见本文档目录中的广播 API 文档。 |
| `target` | String | undefined 或 UUID | 可选，指定接收方 UUID 或识别名，设为 undefined 即全体接收。 |
| `data` | Object | | 需要传递的数据。 |

## target 参数
`target` 参数存在如下几种格式：

- UUID，例如：`2c3103f0-b4ec-4041-b17a-a3d5d19d515a`；
- 识别名，以 `@` 开头。`@__` 开头的识别名为保留识别名，如 `@__server` 指代 WebSocket 服务器。
  - 以 `@` 开头的识别名目前没有任何作用，计划在后续版本加入相关功能。
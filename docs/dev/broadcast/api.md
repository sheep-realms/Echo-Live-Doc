# API 参数格式
Echo-Live 的广播数据是一种 Object 类型的数据，内容如下：

| 键名 | 类型 | 预期值 | 描述 |
| - | - | - | - |
| `action` | String | 动作名称 | 见本文档目录中的广播 API 文档。 |
| `target` | String | undefined 或 UUID | 可选，指定接收方 UUID，设为 undefined 即全体接收。 |
| `data` | Object | | 需要传递的数据。 |
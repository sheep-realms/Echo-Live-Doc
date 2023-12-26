# page_visible
:material-tag:{ title="最早可用版本" .color-indigo } <span class="text-version">1.2.2</span>

Echo-Live 客户端页面重新可见时发送。

## :material-send: 发送数据
| 键名 | 类型 | 预期值 | 描述 |
| - | - | - | - |
| `uuid` | String | UUID | 客户端自己的 UUID。 |

``` javascript title="示例"
{
    action: 'page_visible',
    target: undefined,
    data: {
        uuid: '2c3103f0-b4ec-4041-b17a-a3d5d19d515a'
    }
}
```
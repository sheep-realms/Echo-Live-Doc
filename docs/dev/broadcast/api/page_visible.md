# page_visible
<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.2.2</span>
</span>
<span class="feature-tag" title="终端类型" markdown>
    <span class="icon">:material-application-braces:</span>
    <span class="text">所有客户端</span>
</span>

Echo-Live 客户端页面重新可见时发送。

## :material-send: 发送数据
| 键名 | 类型 | 预期值 | 描述 |
| - | - | - | - |
| `uuid` | String | UUID | 客户端自己的 UUID。 |

``` javascript title="示例"
{
    action: 'page_visible',
    target: undefined,
    type: 'live',
    data: {
        uuid: '2c3103f0-b4ec-4041-b17a-a3d5d19d515a'
    }
}
```
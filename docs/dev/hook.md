# Hook

<span class="feature-tag" title="开发中特性" markdown>
    <span class="icon">:material-update:</span>
    <span class="text">开发中特性</span>
</span>

Hook 是一种在程序运行过程的特定节点注入代码的机制，方便进行二次开发。

Echo-Live 中使用 [`EchoLiveHook`](hook/class/EchoLiveHook.md) 类管理 Hook，您可以通过实例 `echoLiveSystem.hook` 访问到它。

## 使用 Hook

接下来会以一个有趣的小案例讲解如何使用 Hook。此外，[`EchoLiveHookUnit`](hook/class/EchoLiveHookUnit.md) 类是 Hook 单位的实例类型，我们会在接下来的示例中用到它。

`EchoLiveHook` 有一个 `create()` 方法可用于创建 Hook，语法为：

```
create(Hook名称, 方法)
```

Hook 会在被触发时调用传入的方法，并传递参数。一般情况下，传入的参数是 Object 类型，并且具有以下内容：

| 字段名 | 描述 |
| - | - |
| `data` | 触发 Hook 时的业务数据。 |
| `unit` | 触发 Hook 的实例。 |
| `hook` | 触发的 Hook 自身实例。 |

以 `broadcast_terminal_post_message` Hook 为例，其传递参数中的 `data` 字段的值是广播消息内容，我们可以进行以下操作：

``` js linenums="1"
echoLiveSystem.hook.create('broadcast_terminal_post_message', e => {
    // 过滤不是 message_data 的广播 API
	if (e.data.action !== 'message_data') return;

    // 过滤不包含特定语句的消息
    if (e.data.data.messages[0]?.message !== '我是天才！') return;

    // 篡改消息
	e.data.data.messages = [
		{
            message: '我是笨蛋！'
        }
	];

    // 干完就跑
    e.hook.remove();
});
```

!!! tip "温馨提醒"

    未经他人允许篡改他人的消息并不道德，请不要这样做。

以上示例中还使用了 `hook` 字段中传递的 Hook 单位实例并调用其 `remove()` 方法移除 Hook，可以用于仅触发一次或特定条件下不再触发的场景。

## Hook 列表

### 底层系统

| 名称 | 描述 |
| - | - |
| `system_init` | `EchoLiveSystem` 类初始化完成。 |

### 广播

!!! info "注意"

    本小节所提到的对话框、历史记录等客户端均指其在广播系统中的实例，而非其本身的实例。例如，对话框的实例类型为 `EchoLive`，而其在广播系统中的实例类型为 `EchoLiveBroadcastPortal`，本小节指的是后者。

#### 初始化

| 名称 | 描述 |
| - | - |
| `broadcast_terminal_init` | 终端初始化完成。 |
| `broadcast_server_init` | 服务器端初始化完成。 |
| `broadcast_client_init` | 客户端初始化完成。 |
| `broadcast_live_init` | 对话框客户端初始化完成。 |
| `broadcast_history_init` | 历史记录客户端初始化完成。 |

#### 消息收发

| 名称 | 描述 |
| - | - |
| `broadcast_terminal_post_message` | 终端准备发送消息。 |
| `broadcast_terminal_get_message` | 终端收到消息，未验证是否应当接收。 |
| `broadcast_terminal_get_message_valid` | 终端收到消息，已验证应当接收，下同。 |
| `broadcast_server_get_message_valid` | 服务器端收到消息。 |
| `broadcast_client_get_message_valid` | 客户端收到消息。 |
| `broadcast_live_get_message_valid` | 对话框客户端收到消息。 |
| `broadcast_history_get_message_valid` | 历史记录客户端收到消息。 |

### Echo-Live 主要功能

#### 对话框

| 名称 | 描述 |
| - | - |
| `echolive_portal_init` | 对话框初始化完成。 |

#### 历史记录

| 名称 | 描述 |
| - | - |
| `echolive_history_init` | 历史记录初始化完成。 |
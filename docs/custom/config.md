# 配置

`config.json` 是配置文件，您可以在这里更改配置。

## Echo 相关配置
| 配置项 | 预设值 | 描述 |
| - | - | - |
| `print_speed` | 30 | 滚动速度，每个字符打印循环的延迟时间（毫秒），最小值为 4。 |

## Echo Live 相关配置
| 配置项 | 预设值 | 描述 |
| - | - | - |
| `broadcast_enable` | true | 启用广播，可通过编辑器直接发送消息，启用此项将禁用消息轮询。 |
| `broadcast_channel` | 'sheep-realms:echolive' | 广播频道名称。 |
| `messages_polling_enable` | true | 启用消息轮询，无需手动刷新，关闭则使用旧版手动操作。 |
| `messages_polling_tick` | 250 | 消息轮询间隔（毫秒），值越小响应越快，性能消耗越高。 |
| `sleep_enable` | true | 启用休眠机制，当页面不可见时休眠以防止计时器失效所引发的灾难性演出。 |
| `print_audio_enable` | false | 启用打字音效，false 为禁用，true 为启用。 |
| `print_audio_name` | 'typewriter_loop' | 音效名称（详见 res/script/sounds.js）。 |
| `print_audio_volume` | 0.5 | 音效音量，1 为最大。 |
| `print_audio_rate` | 1 | 音效播放速度，1 为原速。 |
| `next_audio_enable` | false | 启用新对话入场音效，false 为禁用，true 为启用。 |
| `next_audio_name` | 'enter' | 音效名称（详见 res/script/sounds.js）。 |
| `next_audio_volume` | 0.5 | 音效音量，1 为最大。 |
| `next_audio_rate` | 1 | 音效播放速度，1 为原速。 |

## 编辑器相关配置
| 配置项 | 预设值 | 描述 |
| - | - | - |
| `tabpage_config_enable` | true | 显示配置标签页。 |
| `tabpage_output_enable` | true | 显示输出标签页。 |
| `username_init` | '' | 初始说话人。 |
| `output_before` | 'echolive.send(' | 在输出内容之前插入的内容。 |
| `ontput_before_enable` | 1 | 启用上述功能，0 为禁用，1 为启用。 |
| `output_after` | ');' | 在输出内容之后插入的内容。 |
| `ontput_after_enable` | 1 | 启用上述功能，0 为禁用，1 为启用。 |
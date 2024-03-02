# 配置

`config.json` 是配置文件，您可以在这里更改配置。

## 全局配置
| 配置项 | 预设值 | 描述 |
| - | - | - |
| `language` | 'zho-Hans' | 显示语言。可用的配置值见[语言列表](language.md#list)。 |

## Echo 相关配置
| 配置项 | 预设值 | 描述 |
| - | - | - |
| `print_speed` | 30 | 滚动速度，每个字符打印循环的延迟时间（毫秒），最小值为 4。 |

## Echo Live 相关配置
| 配置项 | 预设值 | 描述 |
| - | - | - |
| `live_theme` | 'vanilla' | 主题名称。可用的主题请见[主题列表](theme.md#theme-list)。 |
| `live_theme_script_enable` | false | 启用主题脚本。 |
| `broadcast_enable` | true | 启用广播，可通过编辑器直接发送消息，启用此项将禁用消息轮询。 |
| `broadcast_channel` | 'sheep-realms:echolive' | 广播频道名称。 |
| `websocket_enable` | false | 启用 WebSocket。广播模式下启用 WebSocket 可连接至服务器以从第三方软件获取消息。 |
| `websocket_url` | 'ws://127.0.0.1:3000' | WebSocket 连接地址。 |
| `websocket_reconnect_limit` | 5 | WebSocket 最大重连尝试次数。 |
| `experimental_api_enable` | false | 启用实验性 API。 |
| `messages_polling_enable` | true | 启用消息轮询，无需手动刷新，关闭则使用旧版手动操作。 |
| `messages_polling_tick` | 250 | 消息轮询间隔（毫秒），值越小响应越快，性能消耗越高。 |
| `sleep_enable` | true | 启用休眠机制，当页面不可见时休眠以防止计时器失效所引发的灾难性演出。 |
| `sleep_during_printing_stop_print` | true | 在打印期间休眠立即停止打印。 |
| `print_audio_enable` | false | 启用打字音效，`false` 为禁用，`true` 为启用。 |
| `print_audio_name` | 'typewriter_loop' | 音效名称（详见 res/script/sounds.js）。 |
| `print_audio_volume` | 0.5 | 音效音量，`1` 为最大。 |
| `print_audio_rate` | 1 | 音效播放速度，`1` 为原速。 |
| `next_audio_enable` | false | 启用新对话入场音效，`false` 为禁用，`true` 为启用。 |
| `next_audio_name` | 'enter' | 音效名称（详见 res/script/sounds.js）。 |
| `next_audio_volume` | 0.5 | 音效音量，`1` 为最大。 |
| `next_audio_rate` | 1 | 音效播放速度，`1` 为原速。 |

## 编辑器相关配置
| 配置项 | 预设值 | 描述 |
| - | - | - |
| `tabpage_config_enable` | true | 显示配置标签页。 |
| `tabpage_output_enable` | true | 显示输出标签页。 |
| `client_state_panel_enable` | false | 显示对话框状态仪表板。 |
| `username_init` | '' | 初始说话人。 |
| `output_before` | 'echolive.send(' | 在输出内容之前插入的内容。 |
| `ontput_before_enable` | 1 | 启用上述功能，`0` 为禁用，`1` 为启用。 |
| `output_after` | ');' | 在输出内容之后插入的内容。 |
| `ontput_after_enable` | 1 | 启用上述功能，`0` 为禁用，`1` 为启用。 |
| `history_resend_bubble` | false | 历史消息再次发送时是否使历史记录回到顶部。 |
| `history_maximum` | 128 | 历史消息数量上限。设为 `-1` 则不设上限。 |
| `log_line_maximum` | 512 | 日志行数上限。设为 `-1` 则不设上限。 |
| `palette` | 'all' | 拾色器中启用的色板。设为 `all` 视为启用所有可用色板，否则类型为数组，数组元素为字符串，填写需要启用的色板名称，可排序。 |
| `palette_color_contrast_enable` | false | 拾色器是否启用 WCAG 颜色对比度测试面板。 |
| `palette_color_contrast_background_color` | '#ffffff' | 拾色器 WCAG 颜色对比度测试面板参考背景色。仅支持十六进制颜色码，背景色的 Alpha 通道会被忽略。 |
| `palette_color_contrast_threshold` | 3.8 | 拾色器 WCAG 颜色对比度测试面板对比度参考阈值。 |

## 历史记录相关配置
| 配置项 | 预设值 | 描述 |
| - | - | - |
| `message_list_reverse` | false | 历史记录倒序排列。 |
| `message_item_reverse` | false | 历史记录布局左右翻转。 |
| `display_username` | true | 显示说话人。 |
| `display_time` | true | 显示发送时间。 |
| `remove_continuous_duplicate` | true | 去除连续的重复消息。如果场景中有多个对话框同时接收消息，启用此项可避免重复记录历史消息。 |
| `latest_message_hide` | true | 隐藏最新的历史记录。 |

## 无障碍相关配置
| 配置项 | 预设值 | 描述 |
| - | - | - |
| `high_contrast` | false | 高对比度。 |
| `high_contrast_outline_color` | '#00E9FF' | 焦点高亮边框颜色。 |
| `high_contrast_outline_size` | '2px' | 焦点高亮边框尺寸。 |
| `high_contrast_outline_style` | 'solid' | 焦点高亮边框样式。 |
| `drotanopia_and_deuteranopia` | false | 红绿色盲。 |

## 高级设置
除非您知道您在干什么，否则请不要动这里的设置。

| 配置项 | 预设值 | 描述 |
| - | - | - |
| `editor.history_minimum_breaker_threshold` | 128 | 历史记录底部游标熔断阈值。设为 `-1` 可禁用此机制。 |
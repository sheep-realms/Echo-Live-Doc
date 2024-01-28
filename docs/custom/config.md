# 配置

`config.json` 是配置文件，您可以在这里更改配置。

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
| `messages_polling_enable` | true | 启用消息轮询，无需手动刷新，关闭则使用旧版手动操作。 |
| `messages_polling_tick` | 250 | 消息轮询间隔（毫秒），值越小响应越快，性能消耗越高。 |
| `sleep_enable` | true | 启用休眠机制，当页面不可见时休眠以防止计时器失效所引发的灾难性演出。 |
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

## 无障碍相关配置
| 配置项 | 预设值 | 描述 |
| - | - | - |
| `high_contrast` | false | 高对比度。 |
| `drotanopia_and_deuteranopia` | false | 红绿色盲。 |

## 高级设置
除非您知道您在干什么，否则请不要动这里的设置。

| 配置项 | 预设值 | 描述 |
| - | - | - |
| `editor.history_minimum_breaker_threshold` | 128 | 历史记录底部游标熔断阈值。设为 `-1` 可禁用此机制。 |
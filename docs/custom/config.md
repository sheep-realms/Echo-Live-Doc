# 配置

`config.json` 是配置文件，您可以在这里更改配置。

## Echo 相关配置
| 配置项 | 预设值 | 描述 |
| - | - | - |
| `print_speed` | 30 | 滚动速度，每个字符打印循环的延迟时间（毫秒），最小值为 4。 |
| `print_audio_enable` | false | 启用打字音效，false 为禁用，true 为启用。 |
| `print_audio_name` | 'typewriter' | 音效名称（详见 res/script/sounds.js）。 |
| `print_audio_volume` | 0.5 | 音效音量，1 为最大。 |
| `print_audio_rate` | 1 | 音效播放速度，1 为原速。 |
| `next_audio_enable` | false | 启用新对话入场音效，false 为禁用，true 为启用。 |
| `next_audio_name` | 'enter' | 音效名称（详见 res/script/sounds.js）。 |
| `next_audio_volume` | 0.5 | 音效音量，1 为最大。 |
| `next_audio_rate` | 1 | 音效播放速度，1 为原速。 |

## 编辑器相关配置
| 配置项 | 预设值 | 描述 |
| - | - | - |
| `username_init` | '' | 初始说话人。 |
| `output_before` | 'const data = ' | 在输出内容前插入的内容。 |
| `ontput_before_enable` | 1 | 启用上述功能，0 为禁用，1 为启用。 |
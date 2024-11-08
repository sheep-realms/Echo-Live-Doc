# 音效
您可以在[配置](config.md)中分别开启打字音效和新对话入场音效。

`res/data/sound.js` 中定义了音效，您可以在该文件中找到可用的音效名。根据使用场景分为打字音效和新对话入场音效两种音效，不过这两种音效可以混用，只要您不觉得奇怪就行。

打字音效是每一次打印字符时播放的音效。由于中日韩统一表意文字的打印速度与其他字符不同，为了保证打字音效的播放频率稳定，一些字符可能会被跳过。

新对话入场音效指每次打印新对话时所播放的音效。

在浏览器中预览效果时，一些浏览器的自动播放音频政策会导致您在未点击网页的情况下听不到打字音效，这是正常现象，OBS 内置浏览器无此限制。

`res/audio/` 文件夹存放的是音频文件。

## :material-waveform: 音效列表 { id="list" }
### :material-keyboard: 打字音效
| :material-tag: 音效 ID | :material-help-circle: 描述 |
| - | - |
| `typewriter` | 传统打字机的机械按键声。 |
| `typewriter_loop` | 同上，但是准备了 10 种不同的音频随机播放。 |
| `pencil` | 铅笔在纸上写字，包含 12 种不同的音频。 |
| `sys001` | 清脆短促的系统提示音。 |
| `sys002` | 简单调制的系统提示音。 |
| `sys003` | 冒泡系统提示音。 |

### :material-skip-next: 新对话入场音效
| :material-tag: 音效名 | :material-help-circle: 描述 |
| - | - |
| `enter` | 传统打字机按下回车键。 |
| `paper` | 书本翻页。 |

## :material-import: 添加音效
建议您使用[扩展](extension.md)导入音效。

目前主流浏览器基本都支持 MP3、WAV、OGG 等音频格式，OBS 也是如此，请不要使用一些罕见的格式，这可能会导致无法正常播放。

首先请将音频文件导入到 `res/audio/` 文件夹，当然其他文件夹也可以，请记住其所在路径。

然后打开 `res/data/sound.js` 文件，添加一串新的数据，如下所示，请注意与上一条数据之间需要有逗号分隔：

``` javascript
{
    name: '音效名称',
    path: '文件路径'
}
```

最后，在[配置](config.md)中更改所使用的音效即可。
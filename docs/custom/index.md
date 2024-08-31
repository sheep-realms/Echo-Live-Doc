# 总览

## :material-script-text-play: 启动脚本  { id="start-script" }

启动脚本位于软件根目录中。

| 路径 | 描述 |
| - | - |
| `config.js` | 配置文件。如需修改配置文件，请见[配置](config.md)。 |
| `extensions.js` | 扩展列表。 |
| `start.js` | 对话框启动脚本。 |

## :material-application-outline: 页面 { id="page" }

页面文件位于软件根目录中。

| 路径 | 描述 |
| - | - |
| `editor.html` | 编辑器。广播模式下，需要将其以自定义浏览器停靠窗口的方式导入 OBS。 |
| `history.html` | 供观众查看的历史记录。需以浏览器源的方式导入 OBS 场景中。 |
| `live.html` | 对话框。需以浏览器源的方式导入 OBS 场景中。 |
| `settings.html` | 配置文件编辑器。直接在浏览器中打开即可使用。 |
| `template.html` | 模板编辑器，未开发。通常不会被打包进发行版本中。 |

## :material-brush-variant: 样式 { id="style" }

样式文件位于 `res/style/` 文件夹中，下文的路径以此为起点。

| 路径 | 描述 |
| - | - |
| `live-common/` | 通用样式文件夹。 |
| `live-common/base.css` | 前台页面基础样式。 |
| `live-common/char-indent.css` | 对话框引用符号缩进样式。 |
| `live-common/event-effect.css` | 对话框事件动效样式。 |
| `live-common/font-family.css` | 前台页面字体样式。 |
| `live-common/i18n.css` | 前台页面本地化样式。 |
| `live-theme/` | 主题文件夹，定义了对话框等前台页面的样式。<br>各个主题样式文件中已经整理好了常用变量以供修改。<br>如需切换主题，请见[配置](config.md)。 |
| `echo.css` | 定义了对话框正文的样式。 |
| `editor.css` | 后台页面样式，请不要动它，除非您知道您在做什么。 |
| `editor-accessible.css` | 后台页面无障碍访问样式，请不要动它。 |
| `fh-ui.css` | 后台页面所使用的 UI 库，请不要动它。 |
| `settings.css` | 配置文件编辑器样式，请不要动它。 |

## :material-database: 数据 { id="data" }

数据文件一般位于 `res/data/` 文件夹中，详见[注册表列表](../dev/registry.md#registry-list)

## :material-script-text: 脚本 { id="script" }

脚本文件位于 `res/script/` 文件夹中，下文的路径以此为起点。

| 路径 | 描述 |
| - | - |
| `config-load-fail.js` | 用于配置文件加载失败时触发警告。 |
| `editor.js` | 编辑器脚本。 |
| `editor-common.js` | 后台页面通用脚本。 |
| `history.js` | 历史记录脚本，负责部署 EchoLiveHistory 类。 |
| `live.js` | 部署 Echo 的脚本，主要工作为导入配置、绑定事件、配合 `res/style/echo.css` 解析消息格式。 |
| `live-pre.js` | 预加载脚本，负责导入扩展资源。 |
| `settings.js` | 配置文件编辑器脚本。 |
| `template.js` | 模板编辑器脚本，未使用。 |

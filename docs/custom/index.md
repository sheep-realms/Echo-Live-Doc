# 总览

- `res/style/live-theme/` 是主题文件夹，定义了对话框的样式，默认选中 `vanilla.css`，里面已经整理好了常用变量以供修改。
  - 如需切换主题，请修改 `live.html` 中定义的主题样式，文件中已有注释指引。
- `res/style/echo.css` 定义了对话框正文的样式。
- `res/style/fh-ui.css` 是编辑器所使用的 UI 库，请不要动它，除非您知道您在做什么。
- `res/style/editor.css` 是编辑器所使用的样式，请不要动它，除非您知道您在做什么。
- `config.js` 是配置文件，可修改默认滚动速度等信息。
- `res/script/live.js` 是部署 `res/class/Echo.js` 的脚本，主要工作为导入配置、绑定事件、配合 `res/style/echo.css` 解析消息格式。
- `res/script/live-pre.js` 是在 `live.html` 头部加载的脚本，负责导入扩展资源。
- `res/script/sounds.js` 定义了打字音效。
- `res/script/themes.js` 定义了主题。
- `res/script/palettes.js` 定义了拾色器中的色板。
- `res/class/EchoLive.js` 是业务逻辑类，目前正在封装整理 `res/script/live.js` 中的脚本。
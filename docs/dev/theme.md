# 定制主题

## :material-message-text: 定制对话框
Echo-Live 的演出主体（即 `live.html` 中的 `#echo-live` 元素）DOM 结构如下：

<style>
    .echo-live {
        width: 100%;
    }
    .echo-live .line {
        display: flex;
    }
    .echo-live .line>div {
        flex: 1;
    }
    .echo-live,
    .echo-live .top,
    .echo-live .center,
    .echo-live .bottom,
    .echo-live .top-left,
    .echo-live .top-center,
    .echo-live .top-right,
    .echo-live .center-left,
    .echo-live .center-center,
    .echo-live .center-right,
    .echo-live .bottom-left,
    .echo-live .bottom-center,
    .echo-live .bottom-right,
    .center-center-content,
    .center-center-content>div {
        border: var(--md-default-fg-color--lighter) 1px solid;
        margin: 0.25em;
        padding: 0.25em;
    }
    .echo-live .red,
    .echo-red {
        color: var(--md-code-hl-special-color);
    }
</style>

<div class="echo-live">
    <div class="red">#echo-live</div>
    <div class="top">
        <div>.top</div>
        <div class="line">
            <div class="top-left">.top-left</div>
            <div class="top-center">.top-center</div>
            <div class="top-right">.top-right</div>
        </div>
    </div>
    <div class="center">
        <div>.center</div>
        <div class="line">
            <div class="center-left">.center-left</div>
            <div class="center-center">
                <div>.center-center</div>
                <div class="center-center-content">
                    <div class="name red">.name</div>
                    <div class="content echo-output">.content<span class="red">.echo-output</span></div>
                </div>
            </div>
            <div class="center-right">.center-right</div>
        </div>
    </div>
    <div class="bottom">
        <div>.bottom</div>
        <div class="line">
            <div class="bottom-left">.bottom-left</div>
            <div class="bottom-center">.bottom-center</div>
            <div class="bottom-right">.bottom-right</div>
        </div>
    </div>
</div>

``` html linenums="1" title="源代码示例"
<div id="echo-live">
    <div class="top">
        <div class="top-left"></div>
        <div class="top-center"></div>
        <div class="top-right"></div>
    </div>

    <div class="center">
        <div class="center-left"></div>
        <div class="center-center">
            <div class="name"><!-- 说话人名称 --></div>
            <div class="content echo-output"><!-- 消息内容 --></div>
        </div>
        <div class="center-right"></div>
    </div>

    <div class="bottom">
        <div class="bottom-left"></div>
        <div class="bottom-center">
            <!-- 源文件中这里默认预制了一列 span 元素以模拟工具栏 -->
        </div>
        <div class="bottom-right"></div>
    </div>
</div>
```

<p>其中，<span class="echo-red">高亮</span>的 ID 和类名是重要元素，不可删除。除此之外，您可以删改任意元素。</p>

- `.name` 是对话框中显示说话人的元素，内容会被替换为说话人名称。
- `.content.echo-output` 是对话框中输出消息内容的元素，内容会被替换为消息内容。
- `.bottom-center` 默认放置了模拟视觉小说的对话框工具栏元素，仅作装饰之用，不与脚本逻辑绑定。

另外，Echo-Live 预制了一些主题可供您参考：

- [res/style/live-theme/](https://github.com/sheep-realms/Echo-Live/tree/master/res/style/live-theme){ target="_blank" }

## :material-format-text: 定制文本样式
Echo-Live 的文本样式与主题样式分离，需要由 `res/script/live.js` 中的格式解析函数 `msgStyleGenerator()` 配合。

文本样式目前仍未做好客制化准备，如有需要请您自行阅读相关文件：

- [res/style/echo.css](https://github.com/sheep-realms/Echo-Live/tree/master/res/style/echo.css){ target="_blank" }
- [res/script/live.js](https://github.com/sheep-realms/Echo-Live/tree/master/res/script/live.js){ target="_blank" }
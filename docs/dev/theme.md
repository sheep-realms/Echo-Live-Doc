# 定制主题

## 更改样式变量

Echo-Live 的主题样式文件制作了很多样式变量以方便修改，您可以[使用文本编辑器](../main/faq.md#edit-file)编辑主题文件定制您的主题。

Echo-Live 的样式文件位于 `res/style/` 文件夹中，其中需要您注意的内容如下：

- `live-common/` —— 通用样式文件夹。
    - `font-family.css` —— 定义了所有前台页面的字体，可以在这里修改字体变量更换字体。
- `live-theme/` —— 主题样式文件夹，所有的预制主题都在这里。

以 `font-family.css` 为例，您可以在里面找到以下内容：

``` css
--echo-default-font-family: "思源黑体";
```

`--echo-default-font-family` 是变量名，`思源黑体` 是变量的值。引号 `"` 是为了表示这是一个字符串值，您不需要了解这是什么，您只需要知道只要有引号的地方，您最好别把引号删了。

- 如果您不小心把引号删了，请注意您的输入法，不要补回去一对中文引号 `“”`;

您在修改变量的时候有可能会一不小心把末尾的分号 `;` 删了，这会引发错误，请您注意检查。

- 您甚至有可能为了修正这个错误又补了一个中文的分号 `；`，请注意您的输入法。

用于分隔变量名和值的冒号 `:` 也不应当删除。

- 您知道我要说什么。

假如您想更换字体为得意黑，您应当如此修改：

``` css
--echo-default-font-family: "得意黑";
```

需要注意的是，一些字体的实际名称可能与其对外宣称的名称并不一致，您可以打开其字体文件查看名称。

同理，您也可以在主题样式文件中找到如上变量，它们都放置在开头位置，并且有注释指引。

## 定制参考
### :material-message-text: 对话框
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

<p>其中，<span class="echo-red">高亮</span>的 ID 和类名是重要元素，不可删除，除非您不想看见这些元素。除此之外，您可以删改任意元素。</p>

- `.name` 是对话框中显示说话人的元素，内容会被替换为说话人名称。
- `.content.echo-output` 是对话框中输出消息内容的元素，内容会被替换为消息内容。
- `.bottom-center` 默认放置了模拟视觉小说的对话框工具栏元素，仅作装饰之用，不与脚本逻辑绑定。

另外，Echo-Live 预制了一些主题可供您参考：

- [res/style/live-theme/](https://github.com/sheep-realms/Echo-Live/tree/master/res/style/live-theme){ target="_blank" }

### :material-format-text: 文本样式
Echo-Live 的文本样式与主题样式分离，需要由 `res/script/live.js` 中的格式解析函数 `msgStyleGenerator()` 配合。

文本样式目前仍未做好客制化准备，如有需要请您自行阅读相关文件：

- [res/style/echo.css](https://github.com/sheep-realms/Echo-Live/tree/master/res/style/echo.css){ target="_blank" }
- [res/script/live.js](https://github.com/sheep-realms/Echo-Live/tree/master/res/script/live.js){ target="_blank" }
# 注释

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.4.0</span>
</span>

Echo 可以使用 `ruby` 为文本添加注释。你可以在该字段中写入汉语拼音、假名等字符以用于注音，或是用于其他有趣的玩法。

=== "代码"

    ``` json linenums="1" hl_lines="4"
    {
        "message": {
            "text": "注释",
            "ruby": "zhù shì"
        }
    }
    ```

=== "效果预览"

    <ruby>注释<rt>zhù shì</rt></ruby>
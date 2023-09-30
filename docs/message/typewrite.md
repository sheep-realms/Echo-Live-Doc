# 模拟打字

Echo 具有模拟打字过程的功能，可以使用 `typewrite` 字段模拟打字过程。你可以在该字段中写入汉语拼音、假名等字符以模拟打字，Echo 会在遇到英文单引号 `'` 时立即打印下一个字符，以模拟打字过程中的分词机制。

``` json linenums="1" hl_lines="4"
{
    "message": {
        "text": "凉宫春日",
        "typewrite": "liang'gong'chun'ri"
    }
}
```

你也可以忽略一部分拼音，这样更像是真实的打字过程。

``` json linenums="1" hl_lines="4"
{
    "message": {
        "text": "凉宫春日",
        "typewrite": "liang'gong'ch'r"
    }
}
```

当然，这不局限于汉语拼音，也可以是日语，甚至是其他不是模拟打字的好玩的用法。

``` json linenums="1" hl_lines="4"
{
    "message": {
        "text": "涼宮ハルヒ",
        "typewrite": "suzumiyaharuhi"
    }
}
```
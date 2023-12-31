# start.js

`start.js` 是为 Echo-Live 导入对话数据的脚本，其内容如下：

``` javascript linenums="1"
echolive.send({
    "username": "【说话人】",
    "messages": [
        {
            "message": "这里是说话内容。"
        }
    ]
});
```

提取其中的**消息格式**数据，内容如下：

``` javascript linenums="1"
{
    "username": "【说话人】",
    "messages": [
        {
            "message": "这里是说话内容。"
        }
    ]
}
```

其中，`username` 字段用于在对话框中显示说话人，而 `messages` 字段便是这个部分要讲述的内容。

首先，`messages` 字段是消息列表，Echo 设计之初就有 “消息队列” 的概念，用于连续播放多条消息。该列表中每一段用花括号 `{}` 括起来的内容就是一条消息，我们下文要讲述的 “段落格式” 是指这消息列表中的每一条消息本身。

在开始深入之前，建议您先学习 JSON 的基本知识，这是必要的，应该不会太难：

[JSON 语法 - 菜鸟教程](https://www.runoob.com/json/json-syntax.html){ target="_blank" }
# echo_next

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.2.2</span>
</span>
<span class="feature-tag" title="出站终端类型" markdown>
    <span class="icon">:material-arrow-up:</span>
    <span class="text">服务器</span>
</span>
<span class="feature-tag" title="入站终端类型" markdown>
    <span class="icon">:material-arrow-down:</span>
    <span class="text">对话框</span>
</span>

命令 Echo 打印下一条消息。

## :material-send: 发送数据
此动作不需要发送任何数据。

``` javascript title="示例"
{
    action: 'echo_next',
    /* 这里省略了一部分头部信息 */ 
    data: {}
}
```
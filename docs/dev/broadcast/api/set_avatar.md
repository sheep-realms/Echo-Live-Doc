# set_avatar

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">1.6.0</span>
</span>
<span class="feature-tag" title="出站终端类型" markdown>
    <span class="icon">:material-arrow-up:</span>
    <span class="text">对话框</span>
</span>
<span class="feature-tag" title="入站终端类型" markdown>
    <span class="icon">:material-arrow-down:</span>
    <span class="text">形象播放器</span>
</span>

设置 Echo-Live 形象播放器的形象。

## :material-send: 发送数据
此动作发送的数据为[形象数据](../../../message/character.md)。

``` javascript title="示例"
{
    action: 'set_avatar',
    /* 这里省略了一部分头部信息 */
    data: {
        /* 形象数据 */
    }
}
```
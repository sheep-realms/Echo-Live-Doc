# 参考元数据组件

**参考元数据组件**是一种用于提供诸如作者信息、参考链接等可能具有外部链接、多个项目的数据结构。

## 包含字段

参考元数据组件可以是字符串、对象或数组。当类型为字符串时，等效于仅填写了 `name` 字段。当类型为对象时，等效于仅包含一个对象的数组。

每个数组元素有以下字段：

### `name`

显示名称，支持使用[本地化文本组件](text-component.md)。

### `url`

URL 地址，可选，未填写则不会生成链接。

## 示例

``` json title="简单用例"
{
    "name": "Sheep-realms",
    "url": "https://github.com/sheep-realms"
}
```

``` json title="使用本地化文本组件"
{
    "name": {
        "text": "Sheep-realms", 
        "translate": "author.sheep_realms"
    },
    "url": "https://github.com/sheep-realms"
}
```

``` json title="多个项目"
[
    {
        "name": "Sheep-realms",
        "url": "https://github.com/sheep-realms"
    },
    {
        "name": "Echo 追音"
    }
]
```
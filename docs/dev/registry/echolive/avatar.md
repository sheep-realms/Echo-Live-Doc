# echolive:avatar

<span class="feature-tag" title="最早可用版本" markdown>
    <span class="icon">:material-tag:</span>
    <span class="text">待定</span>
</span>

注册形象，以供形象播放器使用。

## :material-list-box-outline: 属性

| 属性 ||
| - | - |
| 唯一键 | `meta.name` |
| 继承 | 无 |

## :material-code-json: 默认值

``` js
{
    meta: {
        name: 'missingno',
        title: 'missingno',
        title_i18n: '',
        author: 'missingno'
    },
    path: {
        action_i18n: 'common.action.',
        scene_i18n: 'common.scene.',
        images: ''
    },
    default_value: {
        action: {
            idle: undefined,
            review: undefined,
            unknown: undefined
        },
        scene: {
            idle: undefined,
            review: undefined,
            unknown: undefined
        }
    },
    action: [],
    scene: []
}
```
# 浏览器支持情况

本页面列举了 Echo-Live 中所使用的技术，您可以点击相关链接查询您的浏览器是否支持相关技术。

截至 OBS 30.0.2 版本，其内置浏览器使用的是 Chrome 103.0.5060.134。

## 全局
- 【必要】[ECMAScript 2015 (ES6)](https://caniuse.com/es6){ target="_blank" }
    - 浏览器必须支持此项，否则无法正常工作。

## 广播系统
- 【必要】[BroadcastChannel API](https://caniuse.com/broadcastchannel){ target="_blank" }
    - 广播系统依赖此 API 工作。
- 【可选】[WebSocket API](https://caniuse.com/mdn-api_websocket){ target="_blank" }
    - 广播系统的 WebSocket 接口依赖此 API 工作。如果没有使用 WebSocket 接口的需求则不受影响。

## 对话框
- 【可选】[Performance API](https://caniuse.com/mdn-api_performance){ target="_blank" }
    - 对话框依赖此 API 衡量对话框停留时间。如果不启用闲置时自动隐去功能则不受影响。
- 【可选】[SpeechSynthesisUtterance API](https://caniuse.com/mdn-api_speechsynthesisutterance){ target="_blank" }
    - 讲述人功能依赖此 API 工作。

## 配置文件编辑器
- 【可选】[Window API: showOpenFilePicker](https://caniuse.com/mdn-api_window_showopenfilepicker){ target="_blank" }
    - 如果浏览器不支持此 API，将无法打开文件选择窗口，但仍可以通过拖拽文件导入文件。
- 【可选】[Window API: showSaveFilePicker](https://caniuse.com/mdn-api_window_showsavefilepicker){ target="_blank" }
    - 如果浏览器不支持此 API，将无法打开文件保存窗口，并回退为直接下载文件。
- 【可选】[PerformanceObserver API](https://caniuse.com/mdn-api_performanceobserver){ target="_blank" }
    - 仅供调试使用，不会对主要功能产生影响。
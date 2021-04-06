# 国际化

----

### 安装

Bee 组件内部默认使用中文，若希望使用其他语言，则需要进行多语言设置。以英文为例，在 main.js 中：

```js
import Vue from 'vue'
import Bee from 'bee-home'

Vue.use(Bee, {
  i18n: (key, value) => i18n.t(key, value)
})
```

### CDN安装

本地引入Bee文件，在 main.js 中：

```js
Vue.use(window.BEE, {
  i18n: (key, value) => i18n.t(key, value)
})
```

### 其他插件

兼容其他 i18n 插件

```js
import Vue from 'vue'
import Bee from 'bee-home'

Vue.use(Element, {
  i18n: function (path, options) {
    // ...
  }
})
```

目前 Bee 内置了中文和英文，并努力完善中...


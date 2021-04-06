# 快速上手

----

### 全局组件使用

可以在项目的入口文件中引入所有组件或所需组件

```js
import Bee from 'bee-home';
import 'bee-home/lib/index.css';
Vue.use(Bee);

//如果使用字典需要赋值axios为全局
import axios from 'axios';
window.axios=axios
```
### CDN方式

将下载的包放入public目录下新建的lib下

```js
//在index.html引入bee的包
bee.min.js为压缩混淆包
bee.js为没有压缩混淆的包
<link rel="stylesheet" href="/lib/index.css" />
<script src="/lib/bee.min.js"></script>

//在main.js中使用
Vue.use(window.BEE);
```

### 单个组件按需使用

可以局部注册所需的组件，适用于与其他框架组合使用的场景

```js
import { beeInput } from 'bee-home'

export default {
  components: {
    beeInput
  }
}
```

在模板中，用 `<bee-input></bee-input>` 自定义标签的方式使用组件

```html
<template>
  <bee-input />
</template>
```


# BEE-UI

> `BEE-UI` 是一款基于 `Vue` ，以Element-UI为底层的商业业务组件。

### 由来

- 项目需要。
- 根据element-ui为底层，封装成熟业务组件，使商业开发更轻便，更直接


### 安装

```bash
npm install bee-home --save
```

### 使用

#### 全局使用

可以在项目的入口文件中引入所有组件或所需组件

```js
import Bee from 'bee-home' // 引入组件库
import 'bee-home/lib/index.css' // 引入样式库

Vue.use(Bee)
```

在模板中，用 `<bee-form></bee-form>` 自定义标签的方式使用组件

```html
<template>
  <bee-form></bee-form>
</template>
```

#### 自定义主题

可以根据需要，结合element-ui更换主题


### 问题

在使用 `BEE-UI` 时遇到问题，或者有好的建议，欢迎提出来！欢迎志同道合前端友人，一起开发！

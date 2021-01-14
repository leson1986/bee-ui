# Carousel 走马灯 
----
- 滚轮播放

### 基本用法

<div class="demo-block">
    <bee-input v-model="form" placeholder="请输入内容"></bee-input>
</div>
<script>
export default {
    data() {
      return {
        form: '我来测试',
      };
    }
};
</script>

:::demo
```html

<div class="demo-block">
    <bee-input v-model="form" placeholder="请输入内容"></bee-input>
</div>
<script>
export default {
    data() {
      return {
        form: '我来测试',
      };
    }
};
</script>

```
:::

### Input Attributes

| 参数                                  | 说明                      | 类型            | 可选值        | 默认值  |
|-------------------------------------|-------------------------|---------------|------------|------|
| append                              | 后面的辅助文字                 | String/Number | -          | -    |
| appendClick(type=search)            | 搜索点击事件                  | Function      | -          | -    |
| maxRows(type=textarea)              | 最大行/最大值                 | Number        | -          | 4    |
| minRows(type=textarea)              | 最小行/最小值                 | Number        | -          | 2    |
| prepend                             | 前面的辅助文字                 | String/Number | -          | -    |
| showPassword (type=password)v2.6.18 | 密码是否可见,当type=password有效 | Boolean       | true/false | true |
| showWordLimit                       | 是否显示输入字数统计              | String/Number | -          | -    |
| maxlength                           | 原生属性，最大输入长度             | Number        | —          | —    |
| minlength                           | 原生属性，最小输入长度             | Number        | —          | —    |
| prefix-icon                         | 输入框头部图标                 | String        | —          | —    |
| suffix-icon                         | 输入框尾部图标                 | String        | -          | —    |










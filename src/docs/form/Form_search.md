<script>
export default{
  data() {
    return {
      form:{},
      option: {
        submitBtn: false,
        emptyBtn: false,
        labelWidth: 120,
        column: [
          {
            label: '搜索内容',
            prop: 'search',
            type: 'search',
            appendClick:()=>{
             this.$message.success('搜索回调'+this.form.search);
            }
          }
        ]
      }
    }
  }
}
</script>

# 搜索输入框



## 普通用法 
<div class="demo-block">
    <bee-form :option="option" v-model="form" > </bee-form>
</div>

:::demo  
配置`type`为`search`,`appendClick`为点击搜索的回调方法
```html
<bee-form :option="option" v-model="form" > </bee-form>

<script>
export default{
  data() {
    return {
      form:{},
      option: {
        labelWidth: 120,
        column: [
          {
            label: '搜索内容',
            prop: 'search',
            type: 'search',
            appendClick:()=>{
              this.$message.success('搜索回调'+this.form.search);
            }
          }
        ]
      }
    }
  }
}
</script>

```
:::
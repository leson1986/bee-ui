<script>
export default {
  data(){
    return {
       data:[{
         name:'张三'
       }],
       option:{
          card:true,
          searchMenuSpan:6,
          column: [{
            label: '姓名',
            prop: 'name',
            search:true,
          },{
            label: '日期',
            prop: 'date',
            type:'datetime',
            search:true,
          }]
       }
    }
  }
}
</script>

# 卡片模式

## 普通用法

<div class="demo-block">
<bee-crud :option="option"  :data="data" ></bee-crud>
</div>

:::demo  
```html
<bee-crud :option="option"  :data="data" ></bee-crud>
<script>
export default {
  data(){
    return {
       data:[{
         name:'张三'
       }],
       option:{
          card:true,
          searchMenuSpan:6,
          column: [{
            label: '姓名',
            prop: 'name',
            search:true,
          },{
            label: '日期',
            prop: 'date',
            type:'datetime',
            search:true,
          }]
       }
    }
  }
}
</script>

```
:::
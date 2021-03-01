<script>
export default {
  watch:{
    direction(value){
      this.option.dialogDirection=value;
    }
  },
  data(){
    return {
      direction:'rtl',
      list:[{
        id:1,
        name:'张三',
        sex:12
      },{
        id:2,
        name:'李四',
        sex:12
      }],
      option:{
        dialogDirection:'rtl',
        dialogType:'drawer',
        column:[{
          label:'id',
          prop:'id'
        },{
          label:'姓名',
          prop:'name'
        },{
          label:'年龄',
          prop:'sex'
        }]
      }
    }
  }
}
</script>

# 表格抽屉
点击新增或编辑按钮进行体验，同时可以切换弹窗方向
## 基本用法

<div class="demo-block">
<el-radio-group v-model="direction">
  <el-radio label="ltr">从左往右开</el-radio>
  <el-radio label="rtl">从右往左开</el-radio>
  <el-radio label="ttb">从上往下开</el-radio>
  <el-radio label="btt">从下往上开</el-radio>
</el-radio-group>
<br/><br/>
<bee-crud :option="option" :data="list"></bee-crud>
</div>


:::demo 
配置`dialogType`为弹窗的方式,`dialogDirection`为弹窗的位置
```html
<el-radio-group v-model="direction">
  <el-radio label="ltr">从左往右开</el-radio>
  <el-radio label="rtl">从右往左开</el-radio>
  <el-radio label="ttb">从上往下开</el-radio>
  <el-radio label="btt">从下往上开</el-radio>
</el-radio-group>
<br/><br/>
<bee-crud :option="option" :data="list"></bee-crud>
<script>
export default {
  watch:{
    direction(value){
      this.option.dialogDirection=value;
    }
  },
  data(){
    return {
      direction:'rtl',
      list:[{
        id:1,
        name:'张三',
        sex:12
      },{
        id:2,
        name:'李四',
        sex:12
      }],
      option:{
        dialogDirection:'rtl',
        dialogType:'drawer',
        column:[{
          label:'id',
          prop:'id'
        },{
          label:'姓名',
          prop:'name'
        },{
          label:'年龄',
          prop:'sex'
        }]
      }
    }
    }
  }
}
</script>

```
:::
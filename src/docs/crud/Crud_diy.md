<script>
export default {
  data(){
    return {
       page:{
         total:40
       },
       data:[{
         name:'张三',
         age:18,
       }],
       option:{
          column: [{
            label: '姓名',
            prop: 'name',
          },{
            label: '年龄',
            prop: 'age',
          }]
       },
        data2: [
          {
            name:'张三',
            sex:'男'
          }, {
            name:'李四',
            sex:'女'
          }
        ],
        option2: {
          column: [{
            label: '姓名',
            prop: 'name',
            headerslot:true,
          }, {
            label: '年龄',
            prop: 'sex'
          }]
        },
        option3:{
          columnBtn:false,
          refreshBtn:false,
          saveBtn:false,
          updateBtn:false,
          cancelBtn:false,
          addBtn:false,
          delBtn:false,
          editBtn:false,
          page:false,
          align:'center',
          menuAlign:'center',
          column:[
             {
              label:'姓名',
              prop:'name'
            }, {
              label:'性别',
              prop:'sex'
            }
          ]
        },
    }
  },
  methods:{
      beforeOpen(done,type){
        this.type=type;
        done()
      },
      handleAdd(){
        this.$refs.crud.rowAdd();
      },
      handleSave(form,done,loading){
        this.$message.success('新增数据'+ JSON.stringify(form));
      },
      handleUpdate(form,index,done,loading){
        this.$message.success('编辑数据'+ JSON.stringify(form)+'数据序号'+index);
      },
      handleEdit (row, index) {
        this.$refs.crud.rowEdit(row, index);
      },
    }
}
</script>

# 自定卡槽

## 自定义表头

<div class="demo-block">
<bee-crud ref="crud" :option="option2" :data="data2">
  <template slot="nameHeader" slot-scope="{column}">
      <el-tag>{{(column || {}).label}}-{{(column || {}).prop}}</el-tag>
  </template>
</bee-crud>
</div>

:::demo 
```html

<bee-crud ref="crud" :option="option" :data="data">
  <template slot="nameHeader" slot-scope="{column}">
      <el-tag>{{(column || {}).label}}-{{(column || {}).prop}}</el-tag>
  </template>
</bee-crud>
<script>
export default {
    data() {
      return {
        option: {
          column: [{
            label: '姓名',
            prop: 'name',
            headerslot:true,
          }, {
            label: '年龄',
            prop: 'sex'
          }]
        },
        data: [
          {
            name:'张三',
            sex:'男'
          }, {
            name:'李四',
            sex:'女'
          }
        ],
      }
    }
}
</script>

```
:::

## 自定义列

<div class="demo-block">
<bee-crud :data="data2" :option="option3" v-model="user">
  <template slot="name" slot-scope="scope" >
    <el-tag>{{scope}}</el-tag>
  </template>
</bee-crud>
</div>

:::demo 
设置列的属性`slot`为`true`时即可开启自定义模式，在卡槽中指定列的名字即可
```html
<bee-crud :data="data" :option="option" v-model="user">
  <template slot="name" slot-scope="scope" >
    <el-tag>{{scope}}</el-tag>
  </template>
</bee-crud>

<script>
export default {
 data() {
      return {
        user:{},
        data: [
          {
            name:'张三',
            sex:'男'
          }, {
            name:'李四',
            sex:'女'
          }
        ],
        option:{
          page:false,
          align:'center',
          menuAlign:'center',
          column:[
             {
              label:'姓名',
              prop:'name',
              slot:true
            },
            {
              label:'性别',
              prop:'sex'
            }
          ]
        },
      };
    },
  }
</script>
```
:::

## 自定义菜单
<div class="demo-block">
<bee-crud :data="data2" :option="option2">
  <template slot="menuLeft">
    <el-button type="primary" size="small">自定义按钮</el-button>
  </template>
  <template slot="menuRight">
     <el-button type="primary" icon="el-icon-edit" circle size="small"></el-button>
  </template>
</bee-crud>
</div>


:::demo  配置`slot`卡槽为`menuLeft`为表单菜单左边位置,卡槽为`menuRight`为表格菜单右边的位置
```html
<bee-crud :data="data" :option="option">
  <template slot="menuLeft">
    <el-button type="primary" size="small">自定义按钮</el-button>
  </template>
  <template slot="menuRight">
     <el-button type="primary" icon="el-icon-edit" circle size="small"></el-button>
  </template>
</bee-crud>

<script>
export default {
    data() {
      return {
        data: [
          {
            name:'张三',
            sex:'男'
          }, {
            name:'李四',
            sex:'女'
          }
        ],
        option:{
          page:false,
          align:'center',
          menuAlign:'center',
          column:[
             {
              label:'姓名',
              prop:'name'
            }, {
              label:'性别',
              prop:'sex'
            }
          ]
        },
      };
    },
}
</script>
```
:::


## 表单按钮自定义
点击编辑或新增--体验

<div class="demo-block">
<bee-crud :data="data2" :option="option3" ref="crud"  :before-open="beforeOpen" @row-save="handleSave" @row-update="handleUpdate">
  <template slot-scope="scope" slot="menuLeft">
    <el-button type="danger"
      icon="el-icon-plus"
      size="small"
      plain
      @click.stop="handleAdd()">新增</el-button>
  </template>
   <template slot-scope="scope" slot="menuForm">
    <el-button type="primary"
                     icon="el-icon-check"
                     size="small"
                     plain
                     v-if="type=='add'"
                     @click="$refs.crud.rowSave()"
                    >自定义新增</el-button>
    <el-button type="primary"
                     icon="el-icon-check"
                     size="small"
                     plain
                    v-if="type=='edit'"
                     @click="$refs.crud.rowUpdate()"
                    >自定义修改</el-button>
   <el-button type="primary"
                     icon="el-icon-check"
                     size="small"
                     plain
                     @click="$refs.crud.closeDialog()"
                    >取消</el-button>
  </template>
  <template slot-scope="scope" slot="menu">
     <el-button type="primary"
                     icon="el-icon-check"
                     size="small"
                     plain
                     @click.stop="handleEdit(scope.row,scope.index)">编辑</el-button>
  </template>
</bee-crud>
</div>

:::demo  
按钮的显隐全部接受`Boolean`类型的值;`columnBtn`为列动态显隐按钮;`refreshBtn`刷新按钮;`addBtn`表格新增按钮;`editBtn`行编辑按钮;`delBtn`行删除按钮;自定义按钮调用组件中对应方法即可,例如编辑方法`rowEdit`
```html
<bee-crud :data="data" :option="option" ref="crud"  :before-open="beforeOpen" @row-save="handleSave" @row-update="handleUpdate">
  <template slot-scope="scope" slot="menuLeft">
    <el-button type="danger"
      icon="el-icon-plus"
      size="small"
      plain
      @click.stop="handleAdd()">新增</el-button>
  </template>
   <template slot-scope="scope" slot="menuForm">
    <el-button type="primary"
                     icon="el-icon-check"
                     size="small"
                     plain
                     v-if="type=='add'"
                     @click="$refs.crud.rowSave()"
                    >自定义新增</el-button>
    <el-button type="primary"
                     icon="el-icon-check"
                     size="small"
                     plain
                    v-if="type=='edit'"
                     @click="$refs.crud.rowUpdate()"
                    >自定义修改</el-button>
   <el-button type="primary"
                     icon="el-icon-check"
                     size="small"
                     plain
                     @click="$refs.crud.closeDialog()"
                    >取消</el-button>
  </template>
  <template slot-scope="scope" slot="menu">
     <el-button type="primary"
                     icon="el-icon-check"
                     size="small"
                     plain
                     @click.stop="handleEdit(scope.row,scope.index)">编辑</el-button>
  </template>
</bee-crud>

<script>
export default {
    data() {
      return {
        type:'',
        data: [
          {
            name:'张三',
            sex:'男'
          }, {
            name:'李四',
            sex:'女'
          }
        ],
        option:{
          columnBtn:false,
          refreshBtn:false,
          saveBtn:false,
          updateBtn:false,
          cancelBtn:false,
          addBtn:false,
          delBtn:false,
          editBtn:false,
          page:false,
          align:'center',
          menuAlign:'center',
          column:[
             {
              label:'姓名',
              prop:'name'
            }, {
              label:'性别',
              prop:'sex'
            }
          ]
        },
      };
    },
    methods:{
      beforeOpen(done,type){
        this.type=type;
        done()
      },
      handleAdd(){
        this.$refs.crud.rowAdd();
      },
      handleSave(form,done,loading){
        this.$message.success('新增数据'+ JSON.stringify(form));
      },
      handleUpdate(form,index,done,loading){
        this.$message.success('编辑数据'+ JSON.stringify(form)+'数据序号'+index);
      },
      handleEdit (row, index) {
        this.$refs.crud.rowEdit(row, index);
      },
    }
}
</script>
```
:::

## 其它

<div class="demo-block">
<bee-crud :option="option2" :page.sync="page" :data="data2">
  <template slot="header">
    <el-tag size="small">头部卡槽</el-tag>
  </template>
  <template slot="footer">
    <el-tag size="small">尾部卡槽</el-tag>
  </template>
   <template slot="page">
    <el-tag size="small">分页卡槽</el-tag>
  </template>
</bee-crud>
</div>


:::demo
```html
<bee-crud :option="option" :page.sync="page" :data="data">
  <template slot="header">
    <el-tag size="small">头部卡槽</el-tag>
  </template>
  <template slot="footer">
    <el-tag size="small">尾部卡槽</el-tag>
  </template>
   <template slot="page">
    <el-tag size="small">分页卡槽</el-tag>
  </template>
</bee-crud>
<script>
export default {
  data(){
    return {
       page:{
         total:40
       },
        data: [
          {
            name:'张三',
            sex:'男'
          }, {
            name:'李四',
            sex:'女'
          }
        ],
        option:{
          align:'center',
          menuAlign:'center',
          column:[
             {
              label:'姓名',
              prop:'name',
            },
            {
              label:'性别',
              prop:'sex'
            }
          ]
        },
    }
  }
}
</script>

```
:::


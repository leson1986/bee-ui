<script>
export default {
    data () {
      return {
          form:{},
          loading:true,
          data:[
            {
              value:0,
              label:'一级部门',
              children:[
                {
                  value:1,
                  label:'一级部门1',
                },{
                  value:2,
                  label:'一级部门2',
                }
              ]
            },{
              value:3,
              label:'二级部门',
              children:[
                {
                  value:4,
                  label:'二级部门1',
                },{
                  value:5,
                  label:'二级部门2',
                }
              ]
            }
          ],
          option1:{
            title:'我是标题',
            formOption:{
              labelWidth:100,
              column:[{
                  label:'自定义项',
                  prop:'test'
              }],
            },
            lazy: true,
            treeLoad: function (node, resolve) {
              if (node.level === 0) {
                return resolve([{ is_show: true, label: 'region', value: new Date().getTime() }]);
              }
              if (node.level > 2) return resolve([]);
              setTimeout(() => {
                const data = [{
                  label: 'leaf',
                  is_show: true,
                  value: new Date().getTime(),
                  leaf: true
                }, {
                  is_show: true,
                  value: new Date().getTime(),
                  label: 'zone'
                }];

                resolve(data);
              }, 500);
            },
            props:{
              labelText:'标题',
              label:'label',
              value:'value',
              children:'children',
              leaf:'leaf'
            }
          },
          option:{
            title:'我是标题',
            filterText:"搜索关键字自定义",
            defaultExpandAll:true,
            formOption:{
              labelWidth:100,
              column:[{
                  label:'自定义项',
                  prop:'test'
              }],
            },
            props:{
              labelText:'标题',
              label:'label',
              value:'value',
              children:'children'
            }
          }
      }
  },
  mounted(){
    setTimeout(()=>{
      this.loading=false
    },2000)
  },
  methods:{
    tip(data){
        this.$message.success(JSON.stringify(data))
    },
    del(data,done){
      this.$confirm('此操作将永久删除该文件, 是否继续?', '提示', {
        confirmButtonText: '确定',
        cancelButtonText: '取消',
        type: 'warning'
      }).then(() => {
        this.$message.success('删除回调')
        done();
      }).catch(() => {
        this.$message({
          type: 'info',
          message: '已取消删除'
        });          
      });
    },
    update(data,parent,done,loading){
      this.$message.success('更新回调')
      done();
    },
    save(data,parent,done,loading){
      this.$message.success('新增回调')
      this.form.id = new Date().getTime();
      this.form.value=new Date().getTime();
      this.form.children=[];
      done();
    },
    nodeClick(data){
      this.$message.success(JSON.stringify(data))
    }
  }
}
</script>

# Tree 树型

常用的树型组件

## 普通用法
<div class="demo-block">

<bee-tree :loading="loading"  :option="option" :data="data" @node-click="nodeClick" @update="update" @save="save" @del="del" v-model="form">
  <span class="el-tree-node__label" slot-scope="{ node, data }">
    <span>
      <i class="el-icon-user-solid"></i>
      {{ (node || {}).label }}
    </span>
  </span>
  <template slot-scope="scope" slot="menu">
    <div class="avue-tree__item" @click.native="tip(scope.node,scope.data)">自定义按钮</div>
  </template>
</bee-tree>

</div>

:::demo 
`option`配置属性即可,`data`为可配置项目，具体参考下表文档
```html
<bee-tree :loading="loading"  :option="option" :data="data" @node-click="nodeClick" @update="update" @save="save" @del="del" v-model="form">
  <span class="el-tree-node__label" slot-scope="{ node, data }">
    <span>
      <i class="el-icon-user-solid"></i>
      {{ (node || {}).label }}
    </span>
  </span>
  <template slot-scope="scope" slot="menu">
    <div class="avue-tree__item" @click.native="tip(scope.node,scope.data)">自定义按钮</div>
  </template>
</bee-tree>
<script>
export default {
    data () {
      return {
          form:{},
          loading:true,
          data:[
            {
              value:0,
              label:'一级部门',
              children:[
                {
                  value:1,
                  label:'一级部门1',
                },{
                  value:2,
                  label:'一级部门2',
                }
              ]
            },{
              value:3,
              label:'二级部门',
              children:[
                {
                  value:4,
                  label:'二级部门1',
                },{
                  value:5,
                  label:'二级部门2',
                }
              ]
            }
          ],
          option:{
            title:'我是标题',
            filterText:"搜索关键字自定义",
            defaultExpandAll:true,
            formOption:{
              labelWidth:100,
              column:[{
                  label:'自定义项',
                  prop:'test'
              }],
            },
            props:{
              labelText:'标题',
              label:'label',
              value:'value',
              children:'children'
            }
          }
      }
  },
  mounted(){
    setTimeout(()=>{
      this.loading=false
    },2000)
  },
  methods:{
    tip(node,data){
        this.$message.success(JSON.stringify(data))
    },
    del(data,done){
      this.$confirm('此操作将永久删除该文件, 是否继续?', '提示', {
        confirmButtonText: '确定',
        cancelButtonText: '取消',
        type: 'warning'
      }).then(() => {
        this.$message.success('删除回调')
        done();
      }).catch(() => {
        this.$message({
          type: 'info',
          message: '已取消删除'
        });          
      });
    },
    update(data,parent,done,loading){
      this.$message.success('更新回调')
      done();
    },
    save(data,parent,done,loading){
      this.$message.success('新增回调')
      this.form.id = new Date().getTime();
      this.form.value=new Date().getTime();
      this.form.children=[];
      done();
    },
    nodeClick(data){
      this.$message.success(JSON.stringify(data))
    }
  }
}
</script>


```
:::


## 懒加载

<div class="demo-block">
<bee-tree :option="option1"  @node-click="nodeClick" @update="update" @save="save" @del="del" v-model="form">
  <template slot-scope="scope" slot="menu">
    <div class="avue-tree__item" @click.native="tip(scope.node,scope.data)">自定义按钮</div>
  </template>
</bee-tree>
</div>

:::demo 

 `lazy`设置为`true`即可，完后在`treeLoad`函数里面处理逻辑，具体看下面例子

```html
<bee-tree :option="option1"  @node-click="nodeClick" @update="update" @save="save" @del="del" v-model="form">
  <template slot-scope="scope" slot="menu">
    <div class="avue-tree__item" @click.native="tip(scope.node,scope.data)">自定义按钮</div>
  </template>
</bee-tree>
<script>
export default {
    data () {
      return {
          form:{},
          option1:{
            title:'我是标题',
            formOption:{
              labelWidth:100,
              column:[{
                  label:'自定义项',
                  prop:'test'
              }],
            },
            lazy: true,
            treeLoad: function (node, resolve) {
              if (node.level === 0) {
                return resolve([{ is_show: true, label: 'region', value: new Date().getTime() }]);
              }
              if (node.level > 2) return resolve([]);
              setTimeout(() => {
                const data = [{
                  label: 'leaf',
                  is_show: true,
                  value: new Date().getTime(),
                  leaf: true
                }, {
                  is_show: true,
                  value: new Date().getTime(),
                  label: 'zone'
                }];

                resolve(data);
              }, 500);
            },
            props:{
              labelText:'标题',
              label:'label',
              value:'value',
              children:'children',
              leaf:'leaf'
            }
          }
      }
  },
  methods:{
    tip(node,data){
        this.$message.success(JSON.stringify(data))
    },
    del(data,done){
      this.$confirm('此操作将永久删除该文件, 是否继续?', '提示', {
        confirmButtonText: '确定',
        cancelButtonText: '取消',
        type: 'warning'
      }).then(() => {
        this.$message.success('删除回调')
        done();
      }).catch(() => {
        this.$message({
          type: 'info',
          message: '已取消删除'
        });          
      });
    },
    update(data,done,loading){
      this.$message.success('更新回调')
      done();
    },
    save(data,done,loading){
      this.$message.success('新增回调')
      this.form.id = new Date().getTime();
      this.form.value=new Date().getTime();
      this.form.children=[];
      done();
    },
    nodeClick(data){
      this.$message.success(JSON.stringify(data))
    }
  }
}
</script>


```
:::

## Variables

| 参数      | 说明          | 类型      | 可选值                           | 默认值  |
|---------- |-------------- |---------- |--------------------------------  |-------- |
| option | 组件配置属性，详情见下面Option属性 | Object | — | — |
| data | 存放结构体的数据 | Array | — | — |

## Option Attributes

| 参数      | 说明          | 类型      | 可选值                           | 默认值  |
|---------- |-------------- |---------- |--------------------------------  |-------- |
| defaultExpandAll | 是否展开节点 | Boolean | false / true  | false |
| dialogWidth | 弹出框宽度 | String | - | 50% |
| formOption | 自定义form表单，具体参考avue-form组件(默认自带一个标题的column，可以根据配置去修改) | Object | - | - |
| menu | 菜单栏 | Boolean | false / true  | true |
| addBtn | 新增按钮 | Boolean | false / true  | true |
| editBtn | 编辑按钮 | Boolean | false / true  | true |
| delBtn | 修改按钮 | Boolean | false / true  | true |
| props | 配置选项，具体看下表 | object | - | - |
| filter | 是否显示搜索框 | Boolean | false / true | true |

## Column Attributes

| 参数      | 说明          | 类型      | 可选值                           | 默认值  |
|---------- |-------------- |---------- |--------------------------------  |-------- |
| label | 节点的名称 | String | -  | - |
| value | 节点的值 | String | -  | - |
| id | 节点主键 | String | -  | - |
| children | 子节点 | Array | -  | - |

## Props Attributes

| 参数      | 说明          | 类型      | 可选值                           | 默认值  |
|---------- |-------------- |---------- |--------------------------------  |-------- |
| label | 指定节点标签为节点对象的某个属性值 | string| — | — |
| labelText | 弹窗添加节点的名称 | String | - | 名称 |
| children | 指定子树为节点对象的某个属性值 | string | — | —
| value | 指定节点选择框的值也作为节点的nodeKey | boolean | — | — |

## Events

| 事件名 | 说明 | 参数 |
| ---- | ---- | ---- |
| save | 新增节点回调 | data, parent, done,loading |
| update | 修改节点回调 | data, parent, done,loading |
| del | 删除节点回调 | data, done |

## Scoped Slot

| name | 说明 |
|------|--------|
| menuBtn | 按钮的卡槽 |
| addBtn | 新增按钮卡槽 |
| - | 节点卡槽 |

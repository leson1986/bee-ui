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
        option0:{
          highlightCurrentRow:true,
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
    methods: {
      handleRowDBLClick (row, event) {
        this.$notify({
          showClose: true,
          message: '双击'+JSON.stringify(row),
          type: 'success',
        })
      },
      setCurrent(row) {
        this.$refs.crud.setCurrentRow(row);
      },
      handleCurrentRowChange(val){
          this.$notify({
            showClose: true,
            message: '单选'+JSON.stringify(val),
            type: 'success',
          });
      },
      handleRowClick (row, event, column) {
          this.$notify({
            showClose: true,
            message: '单击'+JSON.stringify(row),
            type: 'success',
          });
        }
    }
}
</script>



# 行操作
## 行单击

<div class="demo-block">
<bee-crud :data="data" :option="option" @row-click="handleRowClick"></bee-crud>
</div>

:::demo 
单击一行数据时回调`row-click`方法,同时返回当前行的`row`数据,`event`当前的操作对象,`column`当前列的属性
```html

<bee-crud :data="data" :option="option" @row-click="handleRowClick"></bee-crud>

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
        }
      };
    },
    methods: {
        handleRowClick (row, event, column) {
          this.$notify({
            showClose: true,
            message: '单击'+JSON.stringify(row),
            type: 'success',
          });
        },
    }
}
</script>
```
:::

## 行双击

<div class="demo-block">
<bee-crud :data="data" :option="option" @row-dblclick="handleRowDBLClick"></bee-crud>
</div>

:::demo 
双击一行数据时回调`row-dblclick`方法,同时返回当前行的`row`数据,`event`当前的操作对象,`column`当前列的属性 
```html

<bee-crud :data="data" :option="option" @row-dblclick="handleRowDBLClick"></bee-crud>

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
        }
      }
    },
    methods: {
       handleRowDBLClick (row, event) {
        this.$notify({
          showClose: true,
          message: '双击'+JSON.stringify(row),
          type: 'success',
        });
      },
    }
}
</script>
```
:::

## 行单选

<div class="demo-block">
<bee-crud ref="crud" :data="data" :option="option0" @current-row-change="handleCurrentRowChange"></bee-crud>
<div style="margin-top: 20px">
    <el-button @click="setCurrent(data[1])">选中第二行</el-button>
    <el-button @click="setCurrent()">取消选择</el-button>
</div>
</div>

:::demo 
单选一行数据时需要设置`highlightCurrentRow`属性为`true`,回调`current-row-change`方法,同时返回当前行的`row`数据,
```html

<bee-crud ref="crud" :data="data" :option="option0" @current-row-change="handleCurrentRowChange"></bee-crud>
<div style="margin-top: 20px">
    <el-button @click="setCurrent(data[1])">选中第二行</el-button>
    <el-button @click="setCurrent()">取消选择</el-button>
</div>

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
        option0:{
          highlightCurrentRow:true,
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
        }
      }
    },
    methods: {
        setCurrent(row) {
          this.$refs.crud.setCurrentRow(row);
        },
        handleCurrentRowChange(val){
          this.$notify({
            showClose: true,
            message: '单选'+JSON.stringify(val),
            type: 'success',
          });
        }
      },
    }
}
</script>
```
:::
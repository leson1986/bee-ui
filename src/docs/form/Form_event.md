<script>
export default {
 data() {
      return {
        obj: {
          name: '点我试试'
        },
        data: [],
        option: {
            emptyBtn: false,
            submitBtn: false,
          column: [{
            label: '姓名',
            prop: 'name',
            change: ({value,column}) => {
              this.$message.success('change 查看控制台')
              console.log('值改变',value,column)
            },
            click: ({value,column}) => {
              this.$message.success('click 查看控制台')
              console.log('点击事件',value,column)
            },
            focus: ({value,column}) => {
              this.$message.success('focus 查看控制台')
              console.log('获取焦点',value,column)
            },
            blur: ({value,column}) => {
              this.$message.success('blur 查看控制台')
              console.log('失去焦点',value,column)
            }
          }]
        }
      }
    }
}
</script>
# 组件事件

- `change`事件
- `click`事件
- `focus`事件
- `blur`事件

## 普通用法 

<div class="demo-block">
    <bee-form :option="option" v-model="obj"></bee-form>
</div>

:::demo  
目前组件有4个事件`change`,`click`,`focus`,`blur`
```html

 <bee-form :option="option" v-model="obj"></bee-form>
<script>
export default {
 data() {
      return {
        obj: {
          name: '点我试试'
        },
        data: [],
        option: {
            emptyBtn: false,
            submitBtn: false,
          column: [{
            label: '姓名',
            prop: 'name',
            change: ({value,column}) => {
              this.$message.success('change 查看控制台')
              console.log('值改变',value,column)
            },
            click: ({value,column}) => {
              this.$message.success('click 查看控制台')
              console.log('点击事件',value,column)
            },
            focus: ({value,column}) => {
              this.$message.success('focus 查看控制台')
              console.log('获取焦点',value,column)
            },
            blur: ({value,column}) => {
              this.$message.success('blur 查看控制台')
              console.log('失去焦点',value,column)
            }
          }]
        }
      }
    }
}
</script>

```
:::

<script>
export default {
 data() {
      return {
        obj: {
          events: '点我试试',
          text1: 0
        },
        data: [],
        option: {
            emptyBtn: false,
            submitBtn: false,
          column: [{
            label: '事件表演',
            prop: 'events',
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
          },
          {
            label: '内容1',
            prop: 'text1',
            type:'radio',
            control:(val,form)=>{
              if(val===0){
                return {
                  text2:{
                    display:true
                  },
                  text3:{
                    label:'内容3'
                  }
                }
              }else{
                return {
                  text2:{
                    display:false
                  },
                  text3:{
                    label:'有没有发现我变了'
                  }
                }
              }
            },
            dicData:[{
              label:'显示',
              value:0
            },{
              label:'隐藏',
              value:1,
            }]
          },{
            label: '内容2',
            prop: 'text2',
            display:true
          },{
            label: '内容3',
            prop: 'text3'
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
- `control`事件

## 普通用法 

<div class="demo-block">
    <bee-form :option="option" v-model="obj"></bee-form>
</div>

:::demo  
目前组件有5个事件`change`,`click`,`focus`,`blur`,`control`,其中`control`事件函数体必须返回对象，返回对象，返回对象（重要的事说三遍！）
```html

 <bee-form :option="option" v-model="obj"></bee-form>
<script>
export default {
 data() {
      return {
        obj: {
          events: '点我试试',
          text1: 0
        },
        data: [],
        option: {
            emptyBtn: false,
            submitBtn: false,
          column: [{
            label: '事件表演',
            prop: 'events',
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
          },
          {
            label: '内容1',
            prop: 'text1',
            type:'radio',
            control:(val,form)=>{
              if(val===0){
                return {
                  text2:{
                    display:true
                  },
                  text3:{
                    label:'内容3'
                  }
                }
              }else{
                return {
                  text2:{
                    display:false
                  },
                  text3:{
                    label:'有没有发现我变了'
                  }
                }
              }
            },
            dicData:[{
              label:'显示',
              value:0
            },{
              label:'隐藏',
              value:1,
            }]
          },{
            label: '内容2',
            prop: 'text2',
            display:true
          },{
            label: '内容3',
            prop: 'text3'
          }]
        }
      }
    }
}
</script>

```
:::

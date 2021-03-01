<script>
export default {
    data() {
      return {
        data: [
          {
            name:'张三',
            money:3000
          }, {
            name:'李四',
            sex:false,
            money:4000
          }, {
            name:'王五',
            sex:false,
            money:2000
          }
        ],
        option:{
          column:[
             {
              label:'姓名',
              prop:'name'
            },{
              label:'工资',
              prop:'money'
            }
          ]
        }
      }
    },
    methods:{
      rowStyle({row,column,rowIndex}){
        if(rowIndex%2===0){
          return {
              backgroundColor:'#eee',
              color:'orange'
          }
        }
      },
      cellStyle({row,column,rowIndex,columnIndex}){
        if(columnIndex==1){
          if(row.money<=3000){
            return {
              color:'green',
              fontWeight:'bold',
              fontSize:'20'
            }
          }else{
            return {
              color:'red',
              fontWeight:'bold',
              fontSize:'20'
            }
          }
        }
      }
    }
}
</script>



# 行 | 单元格样式
## 普通用法

<div class="demo-block">
<bee-crud :data="data" :option="option" :cell-style="cellStyle" :row-style="rowStyle"></bee-crud>
</div>

:::demo 
对开开放了`cell-style`和`row-style`方法
```html
<bee-crud :data="data" :option="option" :cell-style="cellStyle" :row-style="rowStyle"></bee-crud>
<script>
export default {
    data() {
      return {
        data: [
          {
            name:'张三',
            money:3000
          }, {
            name:'李四',
            sex:false,
            money:4000
          }, {
            name:'王五',
            sex:false,
            money:2000
          }
        ],
        option:{
          column:[
             {
              label:'姓名',
              prop:'name'
            },{
              label:'工资',
              prop:'money'
            }
          ]
        }
      }
    },
    methods:{
      rowStyle({row,column,rowIndex}){
        if(rowIndex%2===0){
          return {
              backgroundColor:'#eee',
              color:'red'
          }
        }
      },
      cellStyle({row,column,rowIndex,columnIndex}){
        if(columnIndex==1){
          if(row.money<=3000){
            return {
              color:'green',
              fontWeight:'bold',
              fontSize:'20'
            }
          }else{
            return {
              color:'red',
              fontWeight:'bold',
              fontSize:'20'
            }
          }
        }
      }
    }
}
</script>


```
:::
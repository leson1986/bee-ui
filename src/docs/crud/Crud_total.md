<script>
export default {
  data(){
    return {
       data:[
         {
          sum: 5,
          avg: 10,
          count: 2,
         },{
          sum: 15,
          avg: 20,
          count: 1,
         }
       ],
       option:{
          index:true,
          showSummary: true,
          sumColumnList: [
            {
              label:'自定义前缀:',
              name: 'sum',
              type: 'sum',
              decimals:1
            },
            {
              name: 'avg',
              type: 'avg'
            },
            {
              name: 'count',
              type: 'count'
            }
          ],
          column: [{
            label: '相加',
            prop: 'sum'
          },
          {
            label: '平均值',
            prop: 'avg'
          },
          {
            label: '统计',
            prop: 'count'
          }]
       }
    }
  },
  methods:{
    spanMethod1({ row, column, rowIndex, columnIndex }) {
      if (rowIndex % 2 === 0) {
        if (columnIndex === 0) {
          return [1, 2];
        } else if (columnIndex === 1) {
          return [0, 0];
        }
      }
    },
    spanMethod2({ row, column, rowIndex, columnIndex }) {
      if (columnIndex === 0) {
        if (rowIndex % 2 === 0) {
          return {
            rowspan: 2,
            colspan: 1
          };
        } else {
          return {
            rowspan: 0,
            colspan: 0
          };
        }
      }
    },
  }
}
</script>

# 统计合计

配置相应的属性后，在表格末尾即可达到统计合计功能

## 普通用法

<div class="demo-block">
<bee-crud :data="data" :option="option" @row-dblclick="handleRowDBLClick"></bee-crud>
</div>

:::demo  
`showSummary`设置为`true`即可开启统计合计功能，`sumColumnList`属性配置需要计算的表格列配置，其中`name`为列的`prop`值，`type`为需要计算的类型，目前支持（合计 / 平均 / 统计）三个大功能，后期将会加强表格的计算能力
```html
<bee-crud :option="option" :data="data"></bee-crud>
<script>
export default {
  data(){
    return {
       data:[
         {
          sum: 5,
          avg: 10,
          count: 2,
         },{
          sum: 15,
          avg: 20,
          count: 1,
         }
       ],
       option:{
          index:true,
          showSummary: true,
          sumColumnList: [
            {
              label:'自定义前缀:',
              name: 'sum',
              type: 'sum',
              decimals:1
            },
            {
              name: 'avg',
              type: 'avg'
            },
            {
              name: 'count',
              type: 'count'
            }
          ],
          column: [{
            label: '相加',
            prop: 'sum'
          },
          {
            label: '平均值',
            prop: 'avg'
          },
          {
            label: '统计',
            prop: 'count'
          }]
       }
    }
  }
}
</script>

```
:::

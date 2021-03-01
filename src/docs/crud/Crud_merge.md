<script>
export default {
  data(){
    return {
      option1:{
        page:false,
        border:true,
        menuAlign:'center',
        column:[{
            label:'ID',
            prop:'id'
          },{
            label:'姓名',
            prop:'name'
          }, {
            label:'数值 1',
            prop:'amount1'
          }, {
            label:'数值 2',
            prop:'amount2'
          }, {
            label:'数值 3',
            prop:'amount3'
          }
        ]
      },
      option2:{
        page:false,
        border:true,
        menuAlign:'center',
        column:[{
            label:'ID',
            prop:'id'
          },{
            label:'姓名',
            prop:'name'
          }, {
            label:'数值 1',
            prop:'amount1'
          }, {
            label:'数值 2',
            prop:'amount2'
          }, {
            label:'数值 3',
            prop:'amount3'
          }
        ]
      },
      data1:[{
          id: '12987122',
          name: '王小虎',
          amount1: '234',
          amount2: '3.2',
          amount3: 10
        }, {
          id: '12987123',
          name: '王小虎',
          amount1: '165',
          amount2: '4.43',
          amount3: 12
        }, {
          id: '12987124',
          name: '王小虎',
          amount1: '324',
          amount2: '1.9',
          amount3: 9
        }, {
          id: '12987125',
          name: '王小虎',
          amount1: '621',
          amount2: '2.2',
          amount3: 17
        }, {
          id: '12987126',
          name: '王小虎',
          amount1: '539',
          amount2: '4.1',
          amount3: 15
        }],
       
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

# 合并列与行

## 合并列

<div class="demo-block">
<bee-crud
  :data="data1"
  :option="option1"
  :span-method="spanMethod1"
></bee-crud>
</div>

:::demo 
通过给传入`spanMethod`方法可以实现合并行或列，方法的参数是一个对象，里面包含当前行`row`、当前列`column`、当前行号`rowIndex`、当前列号`columnIndex`四个属性。该函数可以返回一个包含两个元素的数组，第一个元素代表`rowspan`，第二个元素代表`colspan`。 也可以返回一个键名为`rowspan`和`colspan`的对象。

```html
<bee-crud
  :data="data1"
  :option="option1"
  :span-method="spanMethod1"
></bee-crud>

<script>
  export default {
    data() {
      return {
        data1: [
          {
            id: '12987122',
            name: '王小虎',
            amount1: '234',
            amount2: '3.2',
            amount3: 10
          },
          {
            id: '12987123',
            name: '王小虎',
            amount1: '165',
            amount2: '4.43',
            amount3: 12
          },
          {
            id: '12987124',
            name: '王小虎',
            amount1: '324',
            amount2: '1.9',
            amount3: 9
          },
          {
            id: '12987125',
            name: '王小虎',
            amount1: '621',
            amount2: '2.2',
            amount3: 17
          },
          {
            id: '12987126',
            name: '王小虎',
            amount1: '539',
            amount2: '4.1',
            amount3: 15
          }
        ],
        option1: {
          page: false,
          border: true,
          menuAlign: 'center',
          column: [
            {
              label: 'ID',
              prop: 'id'
            },
            {
              label: '姓名',
              prop: 'name'
            },
            {
              label: '数值 1',
              prop: 'amount1'
            },
            {
              label: '数值 2',
              prop: 'amount2'
            },
            {
              label: '数值 3',
              prop: 'amount3'
            }
          ]
        }
      }
    },
    methods: {
      spanMethod1({ row, column, rowIndex, columnIndex }) {
        if (rowIndex % 2 === 0) {
          if (columnIndex === 0) {
            return [1, 2]
          } else if (columnIndex === 1) {
            return [0, 0]
          }
        }
      }
    }
  }
</script>
```

:::

## 合并行

<div class="demo-block">
<bee-crud
  :data="data1"
  :option="option2"
  :span-method="spanMethod2"
></bee-crud>
</div>

:::demo 
通过给传入`spanMethod`方法可以实现合并行或列，方法的参数是一个对象，里面包含当前行`row`、当前列`column`、当前行号`rowIndex`、当前列号`columnIndex`四个属性。该函数可以返回一个包含两个元素的数组，第一个元素代表`rowspan`，第二个元素代表`colspan`。 也可以返回一个键名为`rowspan`和`colspan`的对象。

```html
<bee-crud
  :data="data1"
  :option="option2"
  :span-method="spanMethod2"
></bee-crud>

<script>
  export default {
    data() {
      return {
        data1: [
          {
            id: '12987122',
            name: '王小虎',
            amount1: '234',
            amount2: '3.2',
            amount3: 10
          },
          {
            id: '12987123',
            name: '王小虎',
            amount1: '165',
            amount2: '4.43',
            amount3: 12
          },
          {
            id: '12987124',
            name: '王小虎',
            amount1: '324',
            amount2: '1.9',
            amount3: 9
          },
          {
            id: '12987125',
            name: '王小虎',
            amount1: '621',
            amount2: '2.2',
            amount3: 17
          },
          {
            id: '12987126',
            name: '王小虎',
            amount1: '539',
            amount2: '4.1',
            amount3: 15
          }
        ],
        option2: {
          page: false,
          border: true,
          menuAlign: 'center',
          column: [
            {
              label: 'ID',
              prop: 'id'
            },
            {
              label: '姓名',
              prop: 'name'
            },
            {
              label: '数值 1',
              prop: 'amount1'
            },
            {
              label: '数值 2',
              prop: 'amount2'
            },
            {
              label: '数值 3',
              prop: 'amount3'
            }
          ]
        }
      }
    },
    methods: {
      spanMethod2({ row, column, rowIndex, columnIndex }) {
        if (columnIndex === 0) {
          if (rowIndex % 2 === 0) {
            return {
              rowspan: 2,
              colspan: 1
            }
          } else {
            return {
              rowspan: 0,
              colspan: 0
            }
          }
        }
      }
    }
  }
</script>
```

:::
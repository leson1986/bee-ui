<script>
export default {
    data() {
      return {
        form:{
            datetime:'1398250549123'//时间戳例子
        },
        option:{
          labelWidth:110,
          column: [{
              label: "日期范围",
              prop: "daterange",
              type: "daterange",
              startPlaceholder: '日期开始范围自定义',
              endPlaceholder: '日期结束范围自定义',
          }, {
              label: "时间范围",
              prop:'timerange',
              type: 'timerange',
              startPlaceholder: '时间开始范围自定义',
              endPlaceholder: '时间结束范围自定义',
          }, {
              label: "时间日期范围",
              type: 'datetimerange',
              prop:'datetimerange',
              span:24,
              row:true,
              startPlaceholder: '时间日期开始范围自定义',
              endPlaceholder: '时间日期结束范围自定义',
          }, {
              label: "日期",
              prop: "date",
              type: "date",  
              pickerOptions: {
              disabledDate(time) {
                return time.getTime() > Date.now();
              },
              shortcuts: [{
                text: '今天',
                onClick(picker) {
                  picker.$emit('pick', new Date());
                }
              }, {
                text: '昨天',
                onClick(picker) {
                  const date = new Date();
                  date.setTime(date.getTime() - 3600 * 1000 * 24);
                  picker.$emit('pick', date);
                }
              }, {
                text: '一周前',
                onClick(picker) {
                  const date = new Date();
                  date.setTime(date.getTime() - 3600 * 1000 * 24 * 7);
                  picker.$emit('pick', date);
                }
              }]
            }
          }, {
              label: "时间",
              prop: "time",
              type: "time",
          }, {
              label: "日期时间",
              prop: "datetime",
              type: "datetime",
              format: "yyyy-MM-dd hh:mm:ss",
              valueFormat: "timestamp",
          }, {
              label: "周",
              prop: "week",
              type: "week",
              format: "yyyy 第 WW 周"
          }, {
              label: "月",
              prop: "month",
              type: "month",
          }, {
            label: "月范围",
            prop: "monthrange",
            type: "monthrange",
          }, {
              label: "年",
              prop: "year",
              type: "year",
          }, {
              label: "多个日期",
              prop: "dates",
              type: "dates",
              format: "yyyy-MM-dd hh:mm:ss",
              valueFormat: "yyyy-MM-dd hh:mm:ss",
          }]
        },
      };
    },
    methods: {
     submit(){
       this.$message.success('当前数据'+JSON.stringify(this.form))
     }
    }
}
</script>

# 日期

## 普通用法

<div class="demo-block">
    <bee-form v-model="form" :option="option" @submit="submit"></bee-form>
</div>

:::demo  
```html

<script>
export default {
    data() {
      return {
        form:{
            datetime:'1398250549123'//时间戳例子
        },
        option:{
          labelWidth:110,
          column: [{
              label: "日期范围",
              prop: "daterange",
              type: "daterange",
              startPlaceholder: '日期开始范围自定义',
              endPlaceholder: '日期结束范围自定义',
          }, {
              label: "时间范围",
              prop:'timerange',
              type: 'timerange',
              startPlaceholder: '时间开始范围自定义',
              endPlaceholder: '时间结束范围自定义',
          }, {
              label: "时间日期范围",
              type: 'datetimerange',
              prop:'datetimerange',
              span:24,
              row:true,
              startPlaceholder: '时间日期开始范围自定义',
              endPlaceholder: '时间日期结束范围自定义',
          }, {
              label: "日期",
              prop: "date",
              type: "date",  
              pickerOptions: {
              disabledDate(time) {
                return time.getTime() > Date.now();
              },
              shortcuts: [{
                text: '今天',
                onClick(picker) {
                  picker.$emit('pick', new Date());
                }
              }, {
                text: '昨天',
                onClick(picker) {
                  const date = new Date();
                  date.setTime(date.getTime() - 3600 * 1000 * 24);
                  picker.$emit('pick', date);
                }
              }, {
                text: '一周前',
                onClick(picker) {
                  const date = new Date();
                  date.setTime(date.getTime() - 3600 * 1000 * 24 * 7);
                  picker.$emit('pick', date);
                }
              }]
            }
          }, {
              label: "时间",
              prop: "time",
              type: "time",
          }, {
              label: "日期时间",
              prop: "datetime",
              type: "datetime",
              format: "yyyy-MM-dd hh:mm:ss",
              valueFormat: "timestamp",
          }, {
              label: "周",
              prop: "week",
              type: "week",
              format: "yyyy 第 WW 周"
          }, {
              label: "月",
              prop: "month",
              type: "month",
          }, {
            label: "月范围",
            prop: "monthrange",
            type: "monthrange",
          }, {
              label: "年",
              prop: "year",
              type: "year",
          }, {
              label: "多个日期",
              prop: "dates",
              type: "dates",
              format: "yyyy-MM-dd hh:mm:ss",
              valueFormat: "yyyy-MM-dd hh:mm:ss",
          }]
        },
      };
    },
    methods: {
     submit(){
       this.$message.success('当前数据'+JSON.stringify(this.form))
     }
    }
}
</script>

```
:::
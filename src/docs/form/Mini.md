# Slider 滑块 
----
- 滑块

### 基本用法

<div class="demo-block">
    <bee-form :option="option" v-model="obj">
        <template slot-scope="{row}" slot="input">
            <el-tag>{{row}}</el-tag>
        </template>
    </bee-form>
</div>
<script>
export default {
  data() {
      return {
        obj: {
          dynamic: [{
            input: 1,
            select: 1,
            radio: 1,
          }, {
            input: 2,
            select: 2,
            radio: 1,
          }, ]
        },
        option: {
          labelWidth: 110,
          column: [{
            label: '输入框',
            prop: "input",
            span:12,
            row: true
          },
          {
            label: '子表单',
            prop: 'dynamic',
            type: 'dynamic',
            span:24,
            children: {
              column: [{
                width: 200,
                label: '输入框',
                prop: "input",
                formslot: true,
              }, {
                width: 200,
                label: '选择框',
                prop: "select",
                type: 'select',
                rules:[{
                  type:'number',
                  required:true,
                  message:'请选择选择框',
                }],
                dicData: [{
                  label: '测试1',
                  value: 1
                }, {
                  label: '测试2',
                  value: 2
                }]
              }, {
                width: 200,
                label: '多选',
                prop: "checkbox",
                type: 'checkbox',
                dicData: [{
                  label: '测试1',
                  value: 1
                }, {
                  label: '测试2',
                  value: 2
                }]
              }, {
                width: 200,
                label: '开关',
                prop: "switch",
                type: 'switch',
                dicData: [{
                  label: '测试1',
                  value: 1
                }, {
                  label: '测试2',
                  value: 2
                }]
              }, {
                width: 200,
                label: '数字框',
                prop: "number",
                type: 'number'
              }, {
                label: '备注',
                prop: "textarea",
                type: "textarea",
              }, ]
            }
          },
          ]
        }
      }
  },
  methods:{
    addAll(){
      for(let i=0;i<10;i++){
        this.obj.dynamic.push({
          input: 1,
          select: 1,
          radio: 1,
        })
      }
    }
  }
}
</script>

:::demo
```html


<div class="demo-block">
    <bee-slider v-model="form" :max="100" :min="20"></bee-slider>
</div>
<script>
export default {
    data() {
      return {
        form: 42,
      };
    }
}
</script>
```
:::


### Props
| 参数            | 说明                  | 类型              | 可选值 | 默认值   |
|---------------|---------------------|-----------------|-----|-------|
| min           | 最小值                 | Number          | —   | 0     |
| max           | 最大值                 | Number          | —   | 100   |
| step          | 步长                  | Number          | —   | 1     |
| range         | 是否为范围选择             | Boolean         | —   | false |
| showInput     | 是否显示输入框，仅在非范围选择时有效  | Boolean         | —   | false |
| showStops     | 是否显示间断点             | Boolean         | —   | false |
| formatTooltip | 格式化 tooltip message | Function(value) | —   | —     |


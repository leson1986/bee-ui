<script>
export default {
    computed: {
      title() {
        return this.type === 0 ? '编 辑' : '保 存'
      },
      datetime() {
        return this.obj1.datetime.split('-')
      },
      option1() {
        return {
          detail: this.detail,
          column: [{
            label: '',
            labelWidth: 10,
            prop: 'divider',
            display: !this.detail,
            component: 'elDivider',//ele分割线
            span: 24,
            params: {
              html: '这是一大堆的文字介绍，很长 很长 很长成这是一大堆的文字介绍，很长 很长 很长成这是一大堆的文字介绍，很长 很长 很长成',
              contentPosition: "left",
            }
          }, {
            label: this.detail ? '' : '选择日期',
            labelWidth: this.detail ? 1 : 80,
            span: 12,
            formslot: this.detail,
            prop: 'datetime',
            type: 'datetime',
            format: "yyyy-MM-dd",
            valueFormat: "yyyy-MM-dd"
          }]
        }
      },
    },
    data() {
      return {
        type: 0,
        obj: {},
        detail: true,
        obj1: {
          datetime: '2020-05-01'
        },
        option: {
          detail:true,
          group: [
            {
              label: '用户信息',
              prop: 'jbxx',
              icon: 'el-icon-edit-outline',
              column: [
                {
                  label: '姓名',
                  prop: 'name',
                  detail:true,
                  rules: [
                    {
                      required: true,
                      message: '请输入姓名',
                      trigger: 'blur'
                    }
                  ]
                }
              ]
            }, {
              label: '退款申请',
              prop: 'tksq',
              icon: 'el-icon-view',
              column: [
                {
                  label: '省份',
                  prop: 'province',
                  type: 'select',
                  props: {
                    label: 'name',
                    value: 'code'
                  },
                  dicUrl: `https://cli.avuejs.com/api/area/getProvince`,
                  rules: [
                    {
                      required: true,
                      message: '请选择省份',
                      trigger: 'blur'
                    }
                  ]
                },
                {
                  label: '多选',
                  prop: 'checkbox',
                  type: 'checkbox',
                  all:true,
                  props: {
                    label: 'name',
                    value: 'code'
                  },
                  span: 24,
                  dicUrl: 'https://cli.avuejs.com/api/area/getProvince'
                }
              ]
            }
            , {
              label: '用户信息',
              prop: 'yhxx',
              icon: 'el-icon-edit-outline',
              column: [
                {
                  label: '测试长度',
                  prop: 'len',
                  maxlength: 5,
                }, {
                  label: '测试自定义',
                  prop: 'names',
                  formslot: true
                }
              ]
            }
          ]
        }
      }
    },
    mounted() {
      setTimeout(() => {
        this.obj = {
          name: 'bee',
          province: '110000',
          checkbox: ['110000']
        }
      }, 100)
    },
    methods: {
      handle1() {
        this.detail = !this.detail;
      },
      handle() {
        if(this.type===1){
          this.type=0
          this.option.detail=true;
        }else{
           this.type=1
          this.option.detail=false;
        }
      },
      submit() {
        this.$message.success(JSON.stringify(this.obj))
      }
    }
}
</script>

# 详情


## 分组详情

<div class="demo-block">
  <el-button @click="handle"  style="margin-left: 20px">{{title}}</el-button>
  <bee-form  :option="option" v-model="obj" @submit="submit"></bee-form>
</div>

:::demo  
`detail`控制是否为详情页,单独也可以给某一列配置
```html

  <el-button @click="handle"  style="margin-left: 20px">{{title}}</el-button>
  <bee-form  :option="option" v-model="obj" @submit="submit"></bee-form>
<script>
export default {
    computed: {
      title() {
        return this.type === 0 ? '编 辑' : '保 存'
      }
    },
    data() {
      return {
        type: 0,
        obj: {},
        option: {
          detail:false,
          group: [
            {
              label: '用户信息',
              prop: 'jbxx',
              icon: 'el-icon-edit-outline',
              column: [
                {
                  label: '姓名',
                  prop: 'name',
                  detail:true,
                  rules: [
                    {
                      required: true,
                      message: '请输入姓名',
                      trigger: 'blur'
                    }
                  ]
                }
              ]
            }, {
              label: '退款申请',
              prop: 'tksq',
              icon: 'el-icon-view',
              column: [
                {
                  label: '省份',
                  prop: 'province',
                  type: 'select',
                  props: {
                    label: 'name',
                    value: 'code'
                  },
                  dicUrl: `https://cli.avuejs.com/api/area/getProvince`,
                  rules: [
                    {
                      required: true,
                      message: '请选择省份',
                      trigger: 'blur'
                    }
                  ]
                },
                {
                  label: '多选',
                  prop: 'checkbox',
                  type: 'checkbox',
                  all:true,
                  props: {
                    label: 'name',
                    value: 'code'
                  },
                  span: 24,
                  dicUrl: 'https://cli.avuejs.com/api/area/getProvince'
                }
              ]
            }
            , {
              label: '用户信息',
              prop: 'yhxx',
              icon: 'el-icon-edit-outline',
              column: [
                {
                  label: '测试长度',
                  prop: 'len',
                  maxlength: 5,
                }, {
                  label: '测试自定义',
                  prop: 'names',
                  formslot: true
                }
              ]
            }
          ]
        }
      }
    },
    mounted() {
      setTimeout(() => {
        this.obj = {
          name: 'bee',
          province: '110000',
          checkbox: ['110000']
        }
      }, 100)
    },
    methods: {
      handle() {
        if(this.type===1){
          this.option.detail=true;
        }else{
          this.option.detail=false;
        }
       
      },
      submit() {
        this.$message.success(JSON.stringify(this.obj))
      }
    }
}
</script>
```
:::


## 详情

<div class="demo-block">
    <el-button @click="handle1" style="margin-left: 20px">{{title}}</el-button>
  <bee-form :option="option1" v-model="obj1" @submit="submit">
    <div slot="datetime" slot-scope="{}">
      这是我要选择的日期{{datetime[0]}}年{{datetime[1]}}月{{datetime[2]}}日
    </div>
  </bee-form>
</div>

:::demo  
```html
    <el-button @click="handle1" style="margin-left: 20px">{{title}}</el-button>
  <bee-form :option="option1" v-model="obj1" @submit="submit">
    <div slot="datetime" slot-scope="{}">
      这是我要选择的日期{{datetime[0]}}年{{datetime[1]}}月{{datetime[2]}}日
    </div>
  </bee-form>
<script>
export default {
  computed: {
      datetime() {
        return this.obj1.datetime.split('-')
      },
      option1() {
        return {
          detail: this.detail,
          column: [{
            label: '',
            labelWidth: 10,
            prop: 'divider',
            display: !this.detail,
            component: 'elDivider',//ele分割线
            span: 24,
            params: {
              html: '这是一大堆的文字介绍，很长 很长 很长成这是一大堆的文字介绍，很长 很长 很长成这是一大堆的文字介绍，很长 很长 很长成',
              contentPosition: "left",
            }
          }, {
            label: this.detail ? '' : '选择日期',
            labelWidth: this.detail ? 1 : 80,
            span: 12,
            formslot: this.detail,
            prop: 'datetime',
            type: 'datetime',
            format: "yyyy-MM-dd",
            valueFormat: "yyyy-MM-dd"
          }]
        }
      },
      title() {
        return this.detail ? '编辑' : '保存'
      },
    },
    data() {
      return {
        detail: true,
        obj1: {
          datetime: '2020-05-01'
        }
      }
    },
    methods: {
      handle1() {
        this.detail = !this.detail;
      },
      submit() {
        this.$message.success(JSON.stringify(this.obj))
      }
    }
}
</script>
```
:::



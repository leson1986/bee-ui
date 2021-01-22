<script>
var DIC = {
    VAILD: [{
        label: '真',
        value: 'true',
    }, {
        label: '假',
        value: 'false',
    }],
    SEX: [{
        label: '男',
        value: 0,
    }, {
        label: '女',
        value: 1,
    }]
}
export default {
    data() {
      return {
        obj:{},
        sizeValue:'small',
        obj0:{},
        obj1:{},
        option1:{
          menuSpan:4,
          column: [{
            label: "用户名",
            prop: "username",
            rules: [{
                required: true,
                message: "请输入用户名",
                trigger: "blur"
            }]
          }]
        },
        option0:{
          emptyBtn:false,
          submitBtn:false,
          column: [{
            label: "用户名",
            prop: "username",
            rules: [{
                required: true,
                message: "请输入用户名",
                trigger: "blur"
            }]
          }]
        }
      }
    },
    computed: {
       option(){
         return{
          size:this.sizeValue,
          mockBtn:true,
          submitText: '完成',
          printBtn:true,
          column: [{
                  label: "用户名",
                  prop: "username",
                  tip: '这是信息提示',
                  span: 8,
                  maxlength: 3,
                  suffixIcon: 'el-icon-tickets',
                  prefixIcon: 'el-icon-tickets',
                  minlength: 2,
                    mock:{
                    type:'name',
                    en:true,
                  },
                  rules: [{
                      required: true,
                      message: "请输入用户名",
                      trigger: "blur"
                  }],
                  change:({value,column})=>{
                      this.obj.address=value;
                      this.$message.success('address change')
                  },
                  click:({value,column})=>{
                      this.$message.success('click')
                  }
              },
              {
                  label: "姓名",
                  prop: "name",
                  mock:{
                    type:'name'
                  },
                  span:8
              },
              {
                  label: "密码",
                  prop: "password",
                  type:'password',
                  mock:{
                    type:'name'
                  },
                  span:8
              },
              {
                  label: "类型",
                  prop: "type",
                  type: "select",
                  dicData: DIC.VAILD,
                  span:6,
                  mock:{
                    type:'dic',
                  },
              },
              {
                  label: "权限",
                  prop: "grade",
                  span: 6,
                  type: "checkbox",
                  dicData: DIC.VAILD,
                  mock:{
                    type:'dic',
                  },
              },
              {
                  label: "开关",
                  prop: "switch",
                  span: 6,
                  type: "switch",
                  dicData: DIC.SEX,
                  mock:{
                    type:'dic'
                  },
                  hide: true,
                  row:true,
              },
              {
                  label: "性别",
                  prop: "sex",
                  span: 6,
                  type: "radio",
                  dicData: DIC.SEX,
                  mock:{
                    type:'dic'
                  },
                  change:({value,column})=>{
                      this.$message.success('change')
                  }
              },
              {
                  label: "数字",
                  prop: "number",
                  type: 'number',
                  span: 6,
                  precision:2,
                  mock:{
                    type:'number',
                    max:1,
                    min:2,
                    precision:2
                  },
                  minRows: 0,
                  maxRows: 3,
                  row:true,
              },
              {
                  label: "网站",
                  span: 12,
                  prop: "url",
                  prepend:'http://',
                  mock:{
                    type:'url',
                    header:false,
                  },
                  append:'com',
                  row:true,
              },
              {
                  label: "日期",
                  prop: "date",
                  type: "date",
                  span:8,
                  format:'yyyy-MM-dd',
                  valueFormat:'yyyy-MM-dd',
                  mock:{
                    type:'datetime',
                    format:'yyyy-MM-dd'
                  },
              },
              {
                  label: "日期时间",
                  prop: "datetime",
                  type: "datetime",
                  span:8,
                  format:'yyyy-MM-dd hh:mm:ss',
                  valueFormat:'yyyy-MM-dd hh:mm:ss',
                  mock:{
                    type:'datetime',
                    format:'yyyy-MM-dd hh:mm:ss',
                    now:true,
                  },
              },
                {
                  label: "时间",
                  prop: "time",
                  type: "time",
                  span:8,
                  format:'hh:mm:ss',
                  valueFormat:'hh:mm:ss',
                  mock:{
                    type:'datetime',
                    format:'hh:mm:ss'
                  },
              },
              {
                  label: "地址",
                  span: 24,
                  prop: "address",
                  mock:{
                    type:'county'
                  },
              },{
                  label: "建议",
                  span: 24,
                  prop: "adit",
                  mock:{
                    type:'word',
                    min:10,
                    max:30
                  },
              },{
                  label: "手机号",
                  mock:{
                    type:'phone'
                  },
                  span: 12,
                  prop: "phone",
              }]
          }
       }
    },
    mounted(){
      this.obj={
        username :'ls.c',
        switch:0,
        phone:'15918714404',
        address: '广州打工人'
      }
    },
    methods:{
        handleEmpty(){
          this.$refs.form.resetForm();
        },
        handleSubmit(){
          this.$refs.form.validate((vaild,done)=>{
            if(vaild){
              this.$message.success(JSON.stringify(this.obj0));
              setTimeout(()=>{
                done()
              },2000)
            }
          })
        },
        emptytChange(){
          this.$message.success('清空方法回调');
        },
        submit () {
          this.$message.success('当前数据'+JSON.stringify(this.obj));
        },
        tip(){
          this.$message.success('自定义按钮');
        }
    }
  }
</script>



# 基础使用

## 普通用法

<div class="demo-block">
<el-row style="margin-bottom:20px">
   <el-radio-group v-model="sizeValue">
    <el-radio label="small">默认(small)</el-radio>
    <el-radio label="medium">medium</el-radio>
    <el-radio label="small">small</el-radio>
    <el-radio label="mini">mini</el-radio>
  </el-radio-group>
</el-row>
<bee-form ref="form" v-model="obj" :option="option" @reset-change="emptytChange" @submit="submit">
   <template slot-scope="scope" slot="menuForm">
      <el-button @click="tip">自定义按钮</el-button>
  </template>
</bee-form>
</div>

:::demo  
里面主要包含了`change`和`click`俩个回调方法，返回当前的值`value`和列的属性`column`,`resetForm`清空表单内容，但是默认值不会被清空,`resetChange`为清空方法的回调,如果想阻止依次排列，在组织属性后面加入row为true即可，配置`mock`为`true`，在对应的`column`配置`mock`,配置即可开启数据填充,具体看如下例子
```html
<el-row style="margin-bottom:20px">
   <el-radio-group v-model="sizeValue">
    <el-radio label="small">默认</el-radio>
    <el-radio label="medium">medium</el-radio>
    <el-radio label="small">small</el-radio>
    <el-radio label="mini">mini</el-radio>
  </el-radio-group>
</el-row>
<bee-form ref="form" v-model="obj" :option="option" @reset-change="emptytChange" @submit="submit">
   <template slot-scope="scope" slot="menuForm">
      <el-button @click="tip">自定义按钮</el-button>
  </template>
</bee-form>

<script>
var DIC = {
    VAILD: [{
        label: '真',
        value: 'true'
    }, {
        label: '假',
        value: 'false'
    }],
    SEX: [{
        label: '男',
        value: 0
    }, {
        label: '女',
        value: 1
    }]
}
export default {
    data() {
      return {
        obj:{},
        sizeValue:'small'
      }
    },
    computed: {
       option(){
         return{
          size:this.sizeValue,
          mockBtn:true,
          submitText: '完成',
          printBtn:true,
          column: [{
                  label: "用户名",
                  prop: "username",
                  tip: '这是信息提示',
                  span: 8,
                  maxlength: 3,
                  suffixIcon: 'el-icon-tickets',
                  prefixIcon: 'el-icon-tickets',
                  minlength: 2,
                    mock:{
                    type:'name',
                    en:true,
                  },
                  rules: [{
                      required: true,
                      message: "请输入用户名",
                      trigger: "blur"
                  }],
                  change:({value,column})=>{
                      this.obj.address=value;
                      this.$message.success('address change')
                  },
                  click:({value,column})=>{
                      this.$message.success('click')
                  }
              },
              {
                  label: "姓名",
                  prop: "name",
                  mock:{
                    type:'name'
                  },
                  span:8
              },
              {
                  label: "密码",
                  prop: "password",
                  type:'password',
                  mock:{
                    type:'name'
                  },
                  span:8
              },
              {
                  label: "类型",
                  prop: "type",
                  type: "select",
                  dicData: DIC.VAILD,
                  span:6,
                  mock:{
                    type:'dic',
                  },
              },
              {
                  label: "权限",
                  prop: "grade",
                  span: 6,
                  type: "checkbox",
                  dicData: DIC.VAILD,
                  mock:{
                    type:'dic',
                  },
              },
              {
                  label: "开关",
                  prop: "switch",
                  span: 6,
                  type: "switch",
                  dicData: DIC.SEX,
                  mock:{
                    type:'dic'
                  },
                  hide: true,
                  row:true,
              },
              {
                  label: "性别",
                  prop: "sex",
                  span: 6,
                  type: "radio",
                  dicData: DIC.SEX,
                  mock:{
                    type:'dic'
                  },
                  change:({value,column})=>{
                      this.$message.success('change')
                  }
              },
              {
                  label: "数字",
                  prop: "number",
                  type: 'number',
                  span: 6,
                  precision:2,
                  mock:{
                    type:'number',
                    max:1,
                    min:2,
                    precision:2
                  },
                  minRows: 0,
                  maxRows: 3,
                  row:true,
              },
              {
                  label: "网站",
                  span: 12,
                  prop: "url",
                  prepend:'http://',
                  mock:{
                    type:'url',
                    header:false,
                  },
                  append:'com',
                  row:true,
              },
              {
                  label: "日期",
                  prop: "date",
                  type: "date",
                  span:8,
                  format:'yyyy-MM-dd',
                  valueFormat:'yyyy-MM-dd',
                  mock:{
                    type:'datetime',
                    format:'yyyy-MM-dd'
                  },
              },
              {
                  label: "日期时间",
                  prop: "datetime",
                  type: "datetime",
                  span:8,
                  format:'yyyy-MM-dd hh:mm:ss',
                  valueFormat:'yyyy-MM-dd hh:mm:ss',
                  mock:{
                    type:'datetime',
                    format:'yyyy-MM-dd hh:mm:ss',
                    now:true,
                  },
              },
                {
                  label: "时间",
                  prop: "time",
                  type: "time",
                  span:8,
                  format:'hh:mm:ss',
                  valueFormat:'hh:mm:ss',
                  mock:{
                    type:'datetime',
                    format:'hh:mm:ss'
                  },
              },
              {
                  label: "地址",
                  span: 24,
                  prop: "address",
                  mock:{
                    type:'county'
                  },
              },{
                  label: "建议",
                  span: 24,
                  prop: "adit",
                  mock:{
                    type:'word',
                    min:10,
                    max:30
                  },
              },{
                  label: "手机号",
                  mock:{
                    type:'phone'
                  },
                  span: 12,
                  prop: "phone",
              }]
          }
       }
    },
    mounted(){
      this.obj={
        username :'ls.c',
        switch:0,
        phone:'15918714404'
      }
    },
    methods:{
        emptytChange(){
          this.$message.success('清空方法回调');
        },
        submit () {
          this.$message.success('当前数据'+JSON.stringify(this.obj));
        },
        tip(){
          this.$message.success('自定义按钮');
        }
    }
  }
</script>
```
:::

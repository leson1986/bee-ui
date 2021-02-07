<script>
var baseUrl = 'https://cli.avuejs.com/api/area'
export default {
  data(){
    return {
       form:{
          province: '110000',
          city: '110100',
          area: '110101'
       },
       option:{
        submitBtn: false,
        emptyBtn: false,
          column: [{
            label: '省份',
            prop: 'province',
            type: 'select',
            props: {
              label: 'name',
              value: 'code'
            },
            cascaderItem: ['city', 'area'],
            dicUrl: `${baseUrl}/getProvince`,
            dicFormatter:(res)=>{
              return res.data;//返回字典的层级结构
            },
            rules: [
              {
                required: true,
                message: '请选择省份',
                trigger: 'blur'
              }
            ]
          },{
            label:'文本框1',
            prop:'text1'
          },
          {
            label: '城市',
            prop: 'city',
            type: 'select',
            props: {
              label: 'name',
              value: 'code'
            },
            row: true,
            cascaderIndex:0,
            dicUrl: `${baseUrl}/getCity/{{key}}?province={{province}}`,
            rules: [
              {
                required: true,
                message: '请选择城市',
                trigger: 'blur'
              }
            ]
          },{
            label:'文本框2',
            prop:'text2'
          },{
            label:'文本框3',
            prop:'text3'
          },
          {
            label: '地区',
            prop: 'area',
            type: 'select',
            props: {
              label: 'name',
              value: 'code'
            },
            cascaderIndex:0,
            dicUrl: `${baseUrl}/getArea/{{key}}?city={{city}}`,
            rules: [
              {
                required: true,
                message: '请选择地区',
                trigger: 'blur'
              }
            ]
          }]
       }
    }
  },
  methods:{
    handleSubmit(form){
       this.$message.success(JSON.stringify(this.form))
    }
  }
}
</script>

# 多级联动
- 多个选择框分级联动

## 普通用法

<div class="demo-block">
    <bee-form :option="option" v-model="form" @submit="handleSubmit"></bee-form>
</div>

:::demo  
`cascaderItem`为需要联动的子选择框`prop`值,注意删除key之间的空格，`dicFormatter`自定义数据返回的层级结构,`cascaderIndex`设置默认选择第几项

```html
<bee-form :option="option" v-model="form" @submit="handleSubmit"></bee-form>
<script>
var baseUrl = 'https://cli.avuejs.com/api/area'
export default {
  data(){
    return {
       form:{
          province: '110000',
          city: '110100',
          area: '110101'
       },
       option:{
          column: [{
            label: '省份',
            prop: 'province',
            type: 'select',
            props: {
              label: 'name',
              value: 'code'
            },
            cascaderItem: ['city', 'area'],
            dicUrl: `${baseUrl}/getProvince`,
            dicFormatter:(res)=>{
              return res.data;//返回字典的层级结构
            },
            rules: [
              {
                required: true,
                message: '请选择省份',
                trigger: 'blur'
              }
            ]
          },{
            label:'文本框1',
            prop:'text1'
          },
          {
            label: '城市',
            prop: 'city',
            type: 'select',
            props: {
              label: 'name',
              value: 'code'
            },
            row: true,
            cascaderIndex:0,
            dicUrl: `${baseUrl}/getCity/{{key}}?province={{province}}`,
            rules: [
              {
                required: true,
                message: '请选择城市',
                trigger: 'blur'
              }
            ]
          },{
            label:'文本框2',
            prop:'text2'
          },{
            label:'文本框3',
            prop:'text3'
          },
          {
            label: '地区',
            prop: 'area',
            type: 'select',
            props: {
              label: 'name',
              value: 'code'
            },
            cascaderIndex:0,
            dicUrl: `${baseUrl}/getArea/{{key}}?city={{city}}`,
            rules: [
              {
                required: true,
                message: '请选择地区',
                trigger: 'blur'
              }
            ]
          }]
       }
    }
  },
  methods:{
    handleSubmit(form){
       this.$message.success(JSON.stringify(this.form))
    }
  }
}
</script>


```
:::
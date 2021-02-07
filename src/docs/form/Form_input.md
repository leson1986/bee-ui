<script>
export default{
  data() {
    return {
      form: {
        input:'欢迎使用bee',
        textarea:'欢迎使用bee',
      },
      option1: {
          submitBtn: false,
          emptyBtn: false,
        column: [
         {
            label:'单文本框',
            prop:'input',
         }
        ]
      },
      option2: {
        submitBtn: false,
        emptyBtn: false,
        column: [
         {
            label:'单文本框',
            prop:'input1',
            maxlength:10,
            showWordLimit:true
         }, {
            label:'多文本框',
            prop:'textarea',
            type:'textarea',
            minRows:10,
            maxlength:200,
            span:24,
            showWordLimit:true
         }
        ]
      },
      option3: {
        submitBtn: false,
        emptyBtn: false,
        column: [{
            label: "网站1",
            span: 12,
            prop: "url1",
            prepend:'http://',
            row:true,
        },{
            label: "网站2",
            span: 12,
            prop: "url2",
            append:'com',
            row:true,
        },{
            label: "网站3",
            span: 12,
            prop: "url3",
            prepend:'http://',
            append:'com',
            row:true,
        }]
    }
    }
  }, 
  methods: {
    submit() {
      this.$message.success('当前数据' + JSON.stringify(this.form))
    }
  }
}
</script>

# 文本框

## 普通用法 

<div class="demo-block">
    <bee-form :option="option1" v-model="form" > </bee-form>
</div>

:::demo  
设置 `type` 默认为 `input`
``` html

<bee-form :option="option" v-model="form"> </bee-form>

<script>
    export default {
        data() {
            return {
                form: {
                    input: '欢迎使用bee',
                },
                option: {
                    column: [{
                        label: '单文本框',
                        prop: 'input',
                    }]
                }
            }
        },
        methods: {
            submit() {
                this.$message.success('当前数据' + JSON.stringify(this.form))
            }
        }
    }
</script>
```

:::

## 多行文本框 
- 限制字数显示
<div class="demo-block">
    <bee-form :option="option2" v-model="form" > </bee-form>
</div>

:::demo  
设置 `type` 为 `textarea` ，配置 `showWordLimit` 为 `true` 即可

``` html
<bee-form :option="option" v-model="form"> </bee-form>

<script>
    export default {
        data() {
            return {
                form: {
                    input: '欢迎使用bee',
                    textarea: '欢迎使用bee',
                },
                option: {
                    column: [{
                        label: '单文本框',
                        prop: 'input',
                        maxlength: 10,
                        showWordLimit: true
                    }, {
                        label: '多文本框',
                        prop: 'textarea',
                        type: 'textarea',
                        minRows: 10,
                        maxlength: 200,
                        span: 24,
                        showWordLimit: true
                    }]
                }
            }
        },
        methods: {
            submit() {
                this.$message.success('当前数据' + JSON.stringify(this.form))
            }
        }
    }
</script>
```

:::


## 复合型输入框 
- 可前置或后置元素，一般为标签或按钮
<div class="demo-block">
    <bee-form :option="option3" v-model="form" > </bee-form>
</div>

:::demo  
可通过设置`prepend`和`append`实现前置或者后置效果。

``` html
<bee-form :option="option" v-model="form"> </bee-form>

<script>
    export default {
        data() {
            return {
                form: {
                    input: '欢迎使用bee',
                    textarea: '欢迎使用bee',
                },
                option: {
                    column: [{
                        label: "网站1",
                        span: 12,
                        prop: "url1",
                        prepend:'http://',
                        row:true,
                    },{
                        label: "网站2",
                        span: 12,
                        prop: "url2",
                        append:'com',
                        row:true,
                    },{
                        label: "网站3",
                        span: 12,
                        prop: "url3",
                        prepend:'http://',
                        append:'com',
                        row:true,
                    }]
                }
            }
        },
        methods: {
            submit() {
                this.$message.success('当前数据' + JSON.stringify(this.form))
            }
        }
    }
</script>
```

:::
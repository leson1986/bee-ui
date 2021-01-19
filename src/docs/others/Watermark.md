<script>
export default {
  data(){
    return {
      obj:'',
      create:false
    }
  },
  methods: {
      submit() {
        if(this.create){
          this.$message.success('已经创建水印了')
          return 
        }
        this.create=true;
        this.$message.success('添加水印成功')
        this.obj=this.watermark({text:'BeeUi全局水印演示'})
      },
      del(){
        this.obj.remove();
        this.create=false;
      },
  }
}
</script>

# Watermark 全局水印


<div class="demo-block">
  <el-button @click="submit" type="primary">全局水印</el-button>
  <el-button @click="del" type="danger">删除水印</el-button>
</div>

:::demo 
```html
<div style="width:400px">
  <el-button @click="submit" type="primary">全局水印</el-button>
  <el-button @click="del" type="danger">删除水印</el-button>
</div>
<script>
export default {
  data(){
    return {
      obj:'',
      create:false
    }
  },
  methods: {
      submit() {
        if(this.create){
          this.$message.success('已经创建水印了')
          return 
        }
        this.create=true;
        this.$message.success('添加水印成功')
        this.obj=this.watermark({text:'BeeUi全局水印演示'})
      },
      del(){
        this.obj.remove();
        this.create=false;
      },
  }
}
</script>


```
:::



## Variables

|参数|说明|类型|可选值|默认值|
|-------------|-------------------------------------------------------------|--------|------|------|
|text|水印的文字|String|-|bee商用通用无敌大水印|
|font|水印字体和大小|String|-|30px 黑体|
|textStyle|水印文本对齐方式|String|-|rgba(100,100,100,0.15)|
|degree|水印文本旋转角度|String|-|-20|
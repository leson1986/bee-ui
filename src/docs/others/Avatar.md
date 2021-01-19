<script>
var UserList = ['U', 'Lucy', 'Tom', 'Edward']
var colorList = ['#f56a00', '#7265e6', '#ffbf00', '#00a2ae']
export default {
  data() {
    return {
      avatarValue: UserList[0],
      color: colorList[0],
    }
  },
  methods: {
    changeValue() {
      var index = UserList.indexOf(this.avatarValue)
      this.avatarValue = index < UserList.length - 1 ? UserList[index + 1] : UserList[0]
      this.color = index < colorList.length - 1 ? colorList[index + 1] : colorList[0]
    },
  }
}
</script>


# Avatar 头像
用来代表用户或事物，支持图片、图标或字符展示。

## 形状


<div class="demo-block">
  <div class="bee-line">
    <bee-avatar :size="64" icon="el-icon-circle-plus-outline"></bee-avatar>
    <bee-avatar size="large" icon="el-icon-circle-plus-outline"></bee-avatar>
    <bee-avatar icon="el-icon-circle-plus-outline"></bee-avatar>
    <bee-avatar size="small" icon="el-icon-circle-plus-outline"></bee-avatar>
  </div>
  <br />
  <div class="bee-line">
    <bee-avatar shape="square" :size="64" icon="el-icon-circle-plus-outline"></bee-avatar>
    <bee-avatar shape="square" size="large" icon="el-icon-circle-plus-outline"></bee-avatar>
    <bee-avatar shape="square" icon="el-icon-circle-plus-outline"></bee-avatar>
    <bee-avatar shape="square" size="small" icon="el-icon-circle-plus-outline"></bee-avatar>
  </div>
</div>

:::demo 
头像有三种尺寸，两种形状可选。
```html
  <div class="bee-line">
    <bee-avatar :size="64" icon="el-icon-circle-plus-outline"></bee-avatar>
    <bee-avatar size="large" icon="el-icon-circle-plus-outline"></bee-avatar>
    <bee-avatar icon="el-icon-circle-plus-outline"></bee-avatar>
    <bee-avatar size="small" icon="el-icon-circle-plus-outline"></bee-avatar>
  </div>
  <br />
  <div class="bee-line">
    <bee-avatar shape="square" :size="64" icon="el-icon-circle-plus-outline"></bee-avatar>
    <bee-avatar shape="square" size="large" icon="el-icon-circle-plus-outline"></bee-avatar>
    <bee-avatar shape="square" icon="el-icon-circle-plus-outline"></bee-avatar>
    <bee-avatar shape="square" size="small" icon="el-icon-circle-plus-outline"></bee-avatar>
  </div>
```
:::


## 类型

<div class="demo-block">
  <div class="bee-line">
    <bee-avatar icon="el-icon-circle-plus-outline"></bee-avatar>
    <bee-avatar>U</bee-avatar>
    <bee-avatar>USER</bee-avatar>
    <bee-avatar src="https://zos.alipayobjects.com/rmsportal/ODTLcjxAfvqbxHnVXCYX.png"></bee-avatar>
    <bee-avatar style="color: #f56a00; background-color: #fde3cf">U</bee-avatar>
    <bee-avatar style="background-color:#87d068" icon="el-icon-circle-plus-outline"></bee-avatar>
  </div>
</div>

:::demo 
支持三种类型：图片、Icon 以及字符，其中 Icon 和字符型可以自定义图标颜色及背景色。
```html
  
  <div class="bee-line">
    <bee-avatar icon="el-icon-circle-plus-outline"></bee-avatar>
    <bee-avatar>U</bee-avatar>
    <bee-avatar>USER</bee-avatar>
    <bee-avatar src="https://zos.alipayobjects.com/rmsportal/ODTLcjxAfvqbxHnVXCYX.png"></bee-avatar>
    <bee-avatar style="color: #f56a00; background-color: #fde3cf">U</bee-avatar>
    <bee-avatar style="background-color:#87d068" icon="el-icon-circle-plus-outline"></bee-avatar>
  </div>
```
:::

## 动态

<div class="demo-block">
  <div>
    <bee-avatar shape="square" size="large" :style="{backgroundColor: color, verticalAlign: 'middle'}">
      {{avatarValue}}</bee-avatar>
    <el-button size="small" style="margin-left:16px;vertical-align: 'middle'" @click="changeValue">改变</el-button>
  </div>
</div>


:::demo  
对于字符型的头像，当字符串较长时，字体大小可以根据头像宽度自动调整。
```html
 
  <div>
    <bee-avatar shape="square" size="large" :style="{backgroundColor: color, verticalAlign: 'middle'}">
      {{avatarValue}}</bee-avatar>
    <el-button size="small" style="margin-left:16px;vertical-align: 'middle'" @click="changeValue">改变</el-button>
  </div>
<script>
var UserList = ['U', 'Lucy', 'Tom', 'Edward']
var colorList = ['#f56a00', '#7265e6', '#ffbf00', '#00a2ae']
export default {
  data() {
    return {
      avatarValue: UserList[0],
      color: colorList[0],
    }
  },
  methods: {
    changeValue() {
      var index = UserList.indexOf(this.avatarValue)
      this.avatarValue = index < UserList.length - 1 ? UserList[index + 1] : UserList[0]
      this.color = index < colorList.length - 1 ? colorList[index + 1] : colorList[0]
    },
  }
}
</script>

```
:::


## Variables

|参数|说明|类型|可选值|默认值|
|-------------|-------------------------------------------------------------|--------|------|------|
|icon|设置头像的图标类型|String|-|-|
|shape|指定头像的形状|String|circle/square|circle|
|size|设置头像的大小|String|large/small|-|
|src|	图片类头像的资源地址|String|-|-|

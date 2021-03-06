<script>
export default {
  data(){
    return {
      loading:true,
    }
  }
}
</script>


# Skeleton 骨架屏

- 在需要等待加载内容的位置提供一个占位图。
    - 网络较慢，需要长时间等待加载处理的情况下。
    - 图文信息内容较多的列表/卡片中。

## 水平

<div class="demo-block">

  最简单的占位效果。
  <bee-skeleton></bee-skeleton>
  <br />
  最后一行占满的效果
  <bee-skeleton block></bee-skeleton>
  <br />
  带头像的效果
  <bee-skeleton avatar></bee-skeleton>
  <br />
  自定义行数的效果
  <bee-skeleton avatar :rows="5"></bee-skeleton>
  <br />
  自定义列表的效果
  <bee-skeleton avatar :rows="4" :number="3"></bee-skeleton>
  <br />
  动态切换效果
  <el-switch :active-value="false" :inactive-value="true" v-model="loading" active-color="#13ce66"
    inactive-color="#ff4949">
  </el-switch>
  <bee-skeleton :loading="loading">
    <span>加载的内容</span>
  </bee-skeleton>
</div>

:::demo 
```html
  最简单的占位效果。
  <bee-skeleton></bee-skeleton>
  <br />
  最后一行占满的效果
  <bee-skeleton block></bee-skeleton>
  <br />
  带头像的效果
  <bee-skeleton avatar></bee-skeleton>
  <br />
  自定义行数的效果
  <bee-skeleton avatar :rows="5"></bee-skeleton>
  <br />
  自定义列表的效果
  <bee-skeleton avatar :rows="4" :number="3"></bee-skeleton>
  <br />
  动态切换效果
  <el-switch :active-value="false" :inactive-value="true" v-model="loading" active-color="#13ce66"
    inactive-color="#ff4949">
  </el-switch>
  <bee-skeleton :loading="loading">
    <span>加载的内容</span>
  </bee-skeleton>
<script>

export default {
  data(){
    return {
      loading:true,
    }
  }
}
</script>

```
:::


## Variables

|参数|说明|类型|可选值|默认值|
|-------------|------------|--------|------|------|
|active|是否展示动画效果|Boolean|true/false|true|
|avatar|是否显示头像占位图|String|true/false|false|
|loading|是否显示骨架屏|Boolean|true/false|true|
|rows|设置段落的行数|Number|-|3|
|block|最后一行是否占满|Boolean|true/false|false|
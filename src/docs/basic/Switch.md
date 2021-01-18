# Switch 开关 
----
- 开关

### 基本用法

<div class="demo-block">
    <bee-switch v-model="form" :dic="dic"></bee-switch>
</div>
<script>
export default {
    data() {
        return {
            form: 0,
            dic: [
                {
                    label: "选项1",
                    value: 0,
                },
                {
                    label: "选项2",
                    value: 1,
                },
            ],
        };
    },
};
</script>

:::demo
```html

<div class="demo-block">
    <bee-switch v-model="form" :dic="dic"></bee-switch>
</div>
<script>
export default {
    data() {
        return {
            form: 0,
            dic: [
                {
                    label: "选项1",
                    value: 0,
                },
                {
                    label: "选项2",
                    value: 1,
                },
            ],
        };
    },
};
</script>
```
:::

### 修改颜色

<div class="demo-block">
    <bee-switch v-model="form" :dic="dic"></bee-switch>
</div>
<script>
export default {
    data() {
        return {
            form: 0,
            dic: [
                {
                    label: "选项1",
                    value: 0,
                },
                {
                    label: "选项2",
                    value: 1,
                },
            ],
        };
    },
};
</script>

:::demo
```html

<div class="demo-block">
    <bee-switch v-model="icons" :dic="dic" active-color="#13ce66" inactive-color="#ff4949"></bee-switch>
</div>
<script>
export default {
    data() {
        return {
            icons: 1,
            dic: [
                {
                    label: "选项1",
                    value: 0,
                },
                {
                    label: "选项2",
                    value: 1,
                },
            ],
        };
    },
};
</script>
```
:::

### 图标

<div class="demo-block">
    <bee-switch v-model="icons" :dic="dic" active-color="#13ce66" inactive-color="#ff4949"></bee-switch>
</div>
<script>
export default {
    data() {
        return {
            icons: 1,
            dic: [
                {
                    label: "选项1",
                    value: 0,
                },
                {
                    label: "选项2",
                    value: 1,
                },
            ],
        };
    },
};
</script>

:::demo
```html

<div class="demo-block">
    <bee-switch v-model="form2" :dic="dic2" active-icon-class="el-icon-s-tools" inactive-icon-class="el-icon-setting"></bee-switch>
</div>
<script>
export default {
    data() {
        return {
            form2: 0,
            dic2: [
                {
                    label: "选项1",
                    value: 0,
                },
                {
                    label: "选项2",
                    value: 1,
                },
            ],
        };
    },
};
</script>
```
:::

### Props

| 参数                | 说明                                       | 类型     | 可选值 | 默认值     |
|-------------------|------------------------------------------|--------|-----|---------|
| len               | switch 的宽度（像素）                           | Number | —   | 40      |
| activeIconClass   | switch 打开时所显示图标的类名，设置此项会忽略 active-text   | String | —   | —       |
| inactiveIconClass | switch 关闭时所显示图标的类名，设置此项会忽略 inactive-text | String | —   | —       |
| activeColor       | switch 打开时的背景色                           | String | —   | #409EFF |
| inactiveColor     | switch 关闭时的背景色                           | String | —   | #C0CCDA |


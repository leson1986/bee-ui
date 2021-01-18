# Checkbox 多选项 
----
- 多选项

### 基本用法

<div class="demo-block">
    <bee-checkbox
        v-model="form"
        placeholder="请选择内容"
        :dic="dic"
    ></bee-checkbox>
</div>
<script>
export default {
    data() {
        return {
            form: [0, 1],
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
    <bee-checkbox
        v-model="form"
        placeholder="请选择内容"
        :dic="dic"
    ></bee-checkbox>
</div>
<script>
export default {
    data() {
        return {
            form: [0, 1],
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


### 组

<div class="demo-block">
    <bee-checkbox
        all
        v-model="form"
        placeholder="请选择内容"
        :dic="dic"
    ></bee-checkbox>
</div>

:::demo
```html

<div class="demo-block">
    <bee-checkbox
        v-model="form"
        placeholder="请选择内容"
        :dic="dic"
    ></bee-checkbox>
</div>
<script>
export default {
    data() {
        return {
            form: [0, 1],
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

### Props

| 参数        | 说明                   | 类型      | 可选值        | 默认值   |
|-----------|----------------------|---------|------------|-------|
| all | 是否启动全选               | Boolean | true/false | false |
| border    | 是否显示边框               | Boolean | —          | false |
| button    | 按钮组类型                | Boolean | —          | false |
| min       | 可被勾选的 checkbox 的最小数量 | Number  | —          | —     |
| max       | 可被勾选的 checkbox 的最大数量 | Number  | —          | —     |



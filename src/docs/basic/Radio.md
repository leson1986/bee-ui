# Radio 单选项 
----
- 单选项

### 基本用法

<div class="demo-block">
    <bee-radio v-model="form" :dic="dic"></bee-radio>
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
    <bee-radio v-model="form" :dic="dic"></bee-radio>
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


### Props

| 参数     | 说明     | 类型      | 可选值 | 默认值   |
|--------|--------|---------|-----|-------|
| border | 是否显示边框 | Boolean | —   | false |
| button | 按钮组类型  | Boolean | —   | false |


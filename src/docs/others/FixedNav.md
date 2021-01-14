# FixedNav 固定按钮
----
- 在element-ui的button等组件的基础上，根据业务需求，可以直接使用于页面的按钮组

### 基本用法

<div class="demo-block">
    <bee-fixed-nav :button-list="buttonList"></bee-fixed-nav>
    <bee-fixed-nav :align="alignLeft" :button-list="buttonList"></bee-fixed-nav>
    <bee-fixed-nav :align="alignRight" :button-list="buttonList"></bee-fixed-nav>
</div>
<script>
import { Notification } from "element-ui";
export default {
    data() {
        return {
            alignLeft: 'left',
            alignRight: 'right',
        };
    },
    computed: {
        buttonList() {
            return [
                {
                    label: "按钮1",
                },
                {
                    label: "按钮2",
                    icon: "",
                    type: "success",
                    size: "small",
                    disabled: "disabled",
                    fun: (i) => {
                        this.buttonClick(i)
                    },
                },
                {
                    label: "",
                    icon: "el-icon-message",
                    type: "danger",
                    size: "mini",
                    fun: (i) => {
                        this.buttonClick(i)
                    },
                },
            ];
        },
    },
    methods: {
        buttonClick(index) {
            Notification({
                showClose: true,
                message: "索引" + JSON.stringify(index),
                type: "success",
            });
        }
    }
};
</script>

:::demo
```html

<div class="demo-block">
    <bee-fixed-nav :button-list="buttonList"></bee-fixed-nav>
    <bee-fixed-nav :align="alignLeft" :button-list="buttonList"></bee-fixed-nav>
    <bee-fixed-nav :align="alignRight" :button-list="buttonList"></bee-fixed-nav>
</div>
<script>
import { Notification } from "element-ui";
export default {
    data() {
        return {
            alignLeft: 'left',
            alignRight: 'right',
        };
    },
    computed: {
        buttonList() {
            return [
                {
                    label: "按钮1",
                },
                {
                    label: "按钮2",
                    icon: "",
                    type: "success",
                    size: "small",
                    disabled: "disabled",
                    fun: (i) => {
                        this.buttonClick(i)
                    },
                },
                {
                    label: "",
                    icon: "el-icon-message",
                    type: "danger",
                    size: "mini",
                    fun: (i) => {
                        this.buttonClick(i)
                    },
                },
            ];
        },
    },
    methods: {
        buttonClick(index) {
            Notification({
                showClose: true,
                message: "索引" + JSON.stringify(index),
                type: "success",
            });
        }
    }
};
</script>
```
:::


## Props
|参数|说明|类型|可选值|默认值|
|----------------------|--------------------------------|:--------:|:------------:|:------:|
|buttonList|按钮列表|Array|—|见DefaultProps|
|align|位置|String|left / center / right | center |

## DefaultProps

|参数|说明|类型|可选值|默认值|
|----------------------|--------------------------------|:--------:|:------------:|:------:|
|size|尺寸|String|medium / small / mini|—|
|type|类型|String|primary / success / warning / danger / info / text|—|
|icon|图标类名，具体使用参考element-ui|String|—|—|
|disabled|是否禁用状态|Boolean|—|false|
|fun|点击按钮回调函数，返回参数index|Function(index)|—|-|

# Rate 评分 
----
- 评分

### 基本用法

<div class="demo-block">
    <bee-rate v-model="form"></bee-rate>
</div>
<script>
export default {
    data() {
      return {
        form: 4,
      };
    }
}
</script>

:::demo
```html


<div class="demo-block">
    <bee-rate v-model="form"></bee-rate>
</div>
<script>
export default {
    data() {
      return {
        form: 4,
      };
    }
}
</script>
```
:::


### Props
| 参数            | 说明                                                                    | 类型           | 可选值 | 默认值                                                      |
|---------------|-----------------------------------------------------------------------|--------------|-----|----------------------------------------------------------|
| showText      | 是否显示辅助文字，若为真，则会从 texts 数组中选取当前分数对应的文字内容                               | Boolean      | —   | false                                                    |
| iconClasses   | icon 的类名。若传入数组，共有 3 个元素，为 3 个分段所对应的类名；若传入对象，可自定义分段，键名为分段的界限值，键值为对应的类名 | Array/Object | —   | ['el-icon-star-on', 'el-icon-star-on','el-icon-star-on'] |
| voidIconClass | 未选中 icon 的类名                                                          | String       | —   | el-icon-star-off                                         |
| max           | 最大分值                                                                  | Number       | —   | 5                                                        |
| colors        | icon 的颜色。若传入数组，共有 3 个元素，为 3 个分段所对应的颜色；若传入对象，可自定义分段，键名为分段的界限值，键值为对应的颜色 | Array/Object | —   | ['#F7BA2A', '#F7BA2A', '#F7BA2A']                        |


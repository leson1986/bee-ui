## 共用属性

:::tip
这是type属性可以共用的属性；具体相关控件属性可查看相关控件文档
:::

|参数|说明|类型|可选值|默认值|
|----------------|-----------------------|--------------------|------------------|---------------------|
|addDisabled<tag>表格生效</tag>|表单新增时是否禁止|Boolean|true/false|false|
|addDisplay<tag>表格生效</tag>|表单新增时是否可见|Boolean|true/false|true|
|addDetail<tag>表格生效</tag>|表单新增时是否可查看|Boolean|true/false|false|
|align<tag>表格生效</tag>|对齐方式|String|left/center/right|left|
|cell<tag>表格生效</tag>|行可编辑时，当前列是否可编辑|Boolean|true/false|false|
|editDisabled<tag>表格生效</tag>|表单编辑时是否禁止|Boolean|true/false|false|
|editDisplay<tag>表格生效</tag>|表单编辑是否可见|Boolean|true/false|true|
|editDetail<tag>表格生效</tag>|表单编辑是否查看状态|Boolean|true/false|false|
|filter<tag>表格生效</tag>|是否在动态显隐里面显示|Boolean|true/false|true|
|filterMultiple<tag>表格生效</tag>|数据过滤的选项是否多选|Boolean|true/false|true|
|filters<tag>表格生效</tag>|数据过滤的选项，数组格式，数组中的元素需要有text和value属性。|Array[{text,value}]|-|-|
|filterMethod<tag>表格生效</tag>|数据过滤使用的方法，如果是多选的筛选项，对每一条数据会执行多次，任意一次返回true就会显示。|Function(value,row,column)|-|-|
|fixed<tag>表格生效</tag>|冻结列|Boolean|true/false|false|
|formatter<tag>表格生效</tag>|用来格式化内容|Function(row,value,label,column)|-|-|
|showColumn<tag>表格生效</tag>|是否加入动态现隐列|Boolean|true/false|true|
|sortable<tag>表格生效</tag>|排序|Boolean|true/false|false|
|slot<tag>表格生效</tag>|列自定义|Boolean|true/false|false|
|viewDisplay<tag>表格生效</tag>|表单查看是否可见|Boolean|true/false|true|
|width<tag>表格生效</tag>|列宽度|String|—|auto|
|minWidth<tag>表格生效</tag>|列最小宽度|String|—|auto|
|arrow<tag>分组模式生效</tag>|分组折叠|Boolean|true/false|true|
|row<tag>表单生效</tag>|是否单独成行|Boolean|true/false|false|
|collapse<tag>分组模式生效</tag>|分组默认叠起|Boolean|true/false|false|
|clearable|是否可以清空选项|Boolean|true/false|false|
|disabled|全部是否禁止|Boolean|true/false|false|
|hide<tag>表格生效</tag>|隐藏列|Boolean|true/false|false|
|overHidden<tag>表格生效</tag>|超出隐藏|Boolean|true/false|false|
|slot<tag>表格生效</tag>|表格自定义|Boolean|true/false|false|
|formslot|表单自定义|Boolean|true/false|false|
|typeslot|表单组件自定义|Boolean|true/false|false|
|showColumn<tag>表格生效</tag>|是否加入动态现隐列|Boolean|true/false|true|
|label|列名称|String|—|-|
|labelWidth<tag>表单生效</tag>|列名称宽度|Number|—|-|
|tip<tag>表单生效</tag>|文字提示|String|-|-|
|tipPlacement<tag>表单生效</tag>|文字提示展示方向|String|top-start/top/top-end/left-start/leftleft-end/right-start/right/right-endbottom-start/bottom/bottom-end|-|
|placeholder|辅助语|String|—|请选择/请输入+label|
|prop|列字段|String|—|-|
|bind|深结构绑定|String|—|-|
|readonly|只读|Boolean|true/false|false|
|rules|表单规则,参考ele表单规则配置|Object|-|-|
|size|表单大小|String|medium/small/mini|medium|
|span|表单栅列|Number|-|12|
|gutter|项之间的间|Number|-|20|
|display|全部是否可见|Boolean|true/false|true|
|props|字典的配置(参考下方Props Attributes)|Object|—|-|
|dataType|数据类型[参考配置](#/basic/format)|String|-|-|
|value|默认值|-|—|-|
|dicData<tag>(type=select/tree/checkbox/radio/switch)</tag>|字典数据|Array|—|-|
|dicUrl<tag>(type=select/tree/checkbox/radio/switch)</tag>|字典地址|String|—|-|
|dicMethod|传入字典的请求方式|Stirng|get/post|get|
|dicQuery|传入字典的请求参数|Object|-|-|

## Props Attributes

|参数|说明|类型|可选值|默认值|
|--------|------------------|------|------|------|
|label|字典的名称属性值|String|—|—|
|value|字典的值属性值|String|—|—|
|children|字典的子属性值|String|—|—|
|res|网络字典返回的数据格式|String|—|—|



## Events

|事件名|说明|参数|
|------------------|---------------------------|-------------------------|
|click|点击事件|Function({value,column}){}|
|change|变化事件|Function({value,column}){}|
|focus|聚焦事件|Function({value,column}){}|
|blur|失焦事件|Function({value,column}){}|
|control|控制事件|Function({value,column}){}|
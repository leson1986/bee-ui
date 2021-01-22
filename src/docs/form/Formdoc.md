## FORM文档

## Variables

|参数|说明|类型|可选值|默认值|
|-------------|-------------------------------------------------------------|--------|------|------|
|option|组件配置属性，详情见下面Option属性|Object|—|—|
|upload-before|图片上传前的回调,会暂停图片上传function(file,done,loading)，done用于继续图片上传，loading用于中断操作|Function|—|—|
|upload-after|图片上传后的回调,function(res,done)，done用于结束操作|Function|—|—|
|upload-delete|删除前的回调,返回true/false即可或promise对象function(column)|Function|—|—|
|upload-preview|查看前的回调function(file,column)|Function|—|—|
|upload-error|上传失败错误回调function(error,column)|Function|—|—|
|upload-exceed|上传唱过长度限制回调function(limit,files,fileList,column)|Function|—|—|

## Column Attributes

:::tip
column中的每一项目配置具体参考对应basic属性文档，不写type默认为Input; [type属性文档](#/basic/common)
:::

## Option Attributes

|参数|说明|类型|可选值|默认值|
|-------------|-------------------|-------|---------------------|------|
|card|卡片效果|Boolean|true/false|false|
|emptyBtn|清空按钮|Boolean|true/false|true|
|emptySize|清空按钮的大小|String|medium/mini/small|medium|
|emptyText|清空按钮的文字|String|-|清空|
|enter|回车提交表单|Boolean|true/false|false|
|group|分组|Array|-|-|
|gutter|项之间的间|Number|-|20|
|labelWidth|表单的label宽度|String|-|80|
|labelPosition|表单的label位置|String|left/top/right|left|
|menuBtn|是否显示按钮|Boolean|true/false|true|
|menuSpan|菜单的span|Number|1-24|24|
|menuPosition|按钮的位置|String|left/center/right|center|
|size|表单全局控件的大小|String|medium/mini/small|medium|
|submitBtn|提交按钮|Boolean|true/false|true|
|submitSize|提交按钮的大小|String|medium/mini/small|medium|
|submitText|提交按钮的文字|String|-|提交|


## Events

|事件名|说明|参数|
|------------|------------|----|
|reset-change|重置表单回调||
|submit|表单提交事件||

## Methods
|方法名|说明|参数|
|-------------|--------------------|----|
|getPropRef|获取prop的ref对象|prop|
|clearValidate|清空表单验证。||
|validate|对整个表单进行校验的方法，参数为一个回调函数。该回调函数会在校验结束后被调用，并传入两个参数：是否校验成功和未通过校验的字段。若不传入回调函数，则会返回一个promise||
|resetForm|清空表单数据||
|submit|提交表单数据||

## ScopedSlot

|name|说明|
|----|---|
|列的名称|列自定义列的内容，参数为{row,label,dic,$index}|
|列表单的名称|表单自定义列的内容，参数为{row,label,dic,$index}|
|列表单的名称+Header(nameHeader)|表单分组头部自定义的内容|
|列表单的名称+Type(nameType)|表单自定义列的内容，参数为{row,label,value}|
|menuForm|表单操作按钮的自定义内容,参数为{row,label,dic,$index}|
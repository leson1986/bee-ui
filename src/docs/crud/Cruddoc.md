# CRUD 文档

## Variables

|参数|说明|类型|可选值|默认值|
|----------------------|--------------------------------|--------|------------|------|
|before-open|打开前的回调，会暂停Dialog的打开function(done,type)，done用于关闭Dialog,type为当前窗口的类型|Function|—|—|
|before-close|关闭前的回调，会暂停Dialog的关闭function(done,type)，done用于关闭Dialog,type为当前窗口的类型|Function|—|—|
|cell-class-name|单元格的className的回调方法，也可以使用字符串为所有单元格设置一个固定的className,function({row,column,rowIndex,columnIndex})/String|Function|-|-|
|data|显示的数据|Array|—|—|
|page|分页的变量(需要sync修饰符)|Object|—|—|
|search|搜索的变量(需要sync修饰符)|Object|—|—|
|header-cell-class-name|header-cell-class-name表头单元格的className的回调方法，也可以使用字符串为所有表头单元格设置一个固定的className,function({row,column,rowIndex,columnIndex})/String|Function|-|-|
|option|组件配置属性，详情见下面Option属性|Object|—|—|
|row-class-name|行的className的回调方法，也可以使用字符串为所有行设置一个固定的className,function({row,rowIndex})|Function|-|-|
|span-method|合并行或列的计算方法Function({row,column,rowIndex,columnIndex})|Function|-|-|
|summary-method|自定义的合计计算方法Function({columns,data})|Function|-|-|
|table-loading|表格等待框的控制|Boolean|true/false|false|
|upload-before|图片上传前的回调,会暂停图片上传function(file,done,loading)，done用于继续图片上传，loading用于中断操作|Function|—|—|
|upload-after|图片上传后的回调,function(res,done)，done用于结束操作，loading用于中断操作|Function|—|—|
|upload-delete|删除前的回调,返回true/false即可或promise对象function(column)|Function|—|—|
|upload-preview|查看前的回调function(file,column)|Function|—|—|
|upload-error|上传失败错误回调function(error,column)|Function|—|—|
|upload-exceed|上传超过长度限制回调function(limit,files,fileList,column)|Function|—|—|

## Column Attributes

:::tip
column中的每一项目配置具体参考对应的type属性文档，不写type默认为Input [type属性文档](#/basic/common)
:::

## Option Attributes

|参数|说明|类型|可选值|默认值|
|----------------|------------------------------------------------------------------------------------------------------------------|---------------|---------------------------|--------|
|addBtn|添加按钮|Boolean|true/false|true|
|addTitle|新增窗口文案|String|-|新增|
|addRowBtn|表格行内添加按钮|Boolean|true/false|false|
|align|表格列齐方式|String|left/center/right|left|
|enter|回车提交表单|Boolean|true/false|false|
|border|表格边框|Boolean|true/false|false|
|calcHeight|表格高度差（主要用于减去其他部分让表格高度自适应）|Number|—|auto|selection|
|columnBtn|列显隐按钮|Boolean|true/false|true|
|cellBtn|表格单元格可编辑（当column中有搜索的属性中有cell为true的属性启用，只对type为select和input有作用)|Boolean|true/false|true|
|dateBtn|日期组件按钮|Boolean|true/false|false|
|cancelBtn|行编辑取消按钮|Boolean|true/false|true|
|dateDefault|日期控件默认的值|Boolean|true/false|false|
|delBtn|行内删除按钮|Boolean|true/false|true|
|defaultSort|表格的排序字段{prop:'date',order:'descending'}prop默认排序字段，order排序方式|Object|—|-|
|dialogFullscreen|是否为全屏Dialog|Boolean|true/false|false|
|dialogEscape|是否可以通过按下ESC关闭Dialog|Boolean|true/false|true|
|dialogClickModal|是否可以通过点击modal关闭Dialog|Boolean|true/false|true|
|dialogCloseBtn|是否显示关闭按钮|Boolean|true/false|true|
|dialogModal|是否需要遮罩层|Boolean|true/false|true|
|dialogTop|弹出表单的弹窗具体顶部的距离|String/Number|-|35|
|dialogType|弹出表单的类型|String|dialog / drawer|dialog|
|dialogWidth|弹出表单的弹窗宽度|String/Number|-|60%|
|dialogHeight|弹出表单的弹窗高度|String/Number|-|400|
|defaultExpandAll|是否默认展开所有行，"expand"为true的时候有效|Boolean|true/false|false|
|expandRowKeys|可以通过该属性设置目前的展开行，需要设置 rowKey 属性才能使用，该属性为展开行的 keys 数组。|Array|-|-|
|editBtn|行内编辑按钮|Boolean|true/false|true|
|editTitle|编辑窗口文案|String|-|编辑|
|empty-text|空数据时显示的文本内容，也可以通过slot="empty"设置|String|-|暂无数据|
|expand|是否展开折叠行|Boolean|true/false|false|
|expandWidth|是否展开折叠行宽度|Number|-|50|
|expandFixed|是否展开折叠行冻结|Boolean|true/false|true|
|excelBtn|打印按钮|Boolean|true/false|false|
|filterBtn|自定义过滤按钮|Boolean|true/false|false|
|fit|是列的宽度是否自撑开属性|boolean|true/false|true|
|height|表格高度|Number|—|auto|
|header|头部显隐|Boolean|true/false|true|
|index|是否显示表格序号（根据分页会自动计算，比如每页10行，到了第二页就会从11开始记数）|Boolean|true/false|false|
|indexLabel|序号的标题|String|—|#|
|indexWidth|序号的宽度|Number|—|50|
|indexFixed|序号的是否冻结|Boolean|true / false|true|
|rowKey|行数据的 Key的主键，用于其他相关操作|String|—|id|
|indeterminate|设置 indeterminate 状态，只负责样式控制 如果选择一半，不会出现半选|Boolean|—|false|
|labelWidth|弹出表单的label宽度|Number|-|110|
|maxHeight|表格最大高度|Number|—|auto|
|menu|是否显示操作菜单栏|Boolean|true/false|true|
|menuPosition|按钮的位置|String|left/center/right|right|
|menuWidth|操作菜单栏的宽度|Number|-|240|
|menuXsWidth|手机端时操作菜单栏的宽度|Number|-|100|
|menuAlign|菜单栏对齐方式|String|left/center/right|left|
|menuType|操作栏菜单按钮类型|String|button/icon/text/menu|text|
|menuBtnTitle|菜单按钮的文字|String|-|功能|
|menuTitle|操作列的文字|String|-|操作|
|menuSpan|菜单的span|Number|1-24|24|
|menuFixed|操作列是否冻结|Bool/String|true/false/left/right|right|
|printBtn|打印按钮|Boolean|true/false|false|
|refreshBtn|刷新按钮|Boolean|true/false|true|
|saveBtn|保存按钮|Boolean|true/false|true|
|updateBtn|更新按钮|Boolean|true/false|true|
|cancelBtn|取消按钮|Boolean|true/false|true|
|order|字段排序|Number|-|-|
|selection|行可勾选|Boolean|true/false|false|
|selectionWidth|行可勾选的宽度|Number|-|50|
|selectionFixed|行可勾选是否冻结|Boolean|true/false|true|
|searchBtn|搜索显隐按钮|Boolean|true/false|true|
|selectable|仅对 selection为true 的列有效，类型为 Function，Function 的返回值用来决定这一行的 CheckBox 是否可以勾选|Function(row, index)	|—|—|
|reserveSelection|仅对 selection为true  的列有效，类型为 Boolean，为 true 则会在数据更新之后保留之前选中的数据（需指定 rowKey）|Boolean|true/false|true| 
|selectClearBtn|清空选中按钮（当selection为true起作用）|Boolean|true/false|true|
|showHeader|是否显示表格的表头|Boolean|true/false|true|
|showSummary|是否在表尾显示合计行|Boolean|true/false|false|
|size|控件大小|String|medium/small/mini|medium|
|sumColumnList|表格合计需要配置的字段|Array|-|-|
|stripe|是否显示表格的斑马条纹|Boolean|true/false|false|
|updateBtnTitle|弹出框更新按钮标题|String|—|修改|
|viewBtn|查看按钮|Boolean|true/false|false|
|viewTitle|查看窗口文案|String|-|查看|

## Text Option Attributes
|参数|说明|类型|可选值|默认值|
|------------------|--------------------------------------------------------------------------------------------|----------------------------|------------|------|
|addBtnText|新增按钮|String|-|新增|
|editBtnText|编辑按钮|String|-|编辑|
|delBtnText|删除按钮|String|-|删除|
|viewBtnText|查看按钮|String|-|查看|
|searchBtnText|搜索按钮|String|-|搜索|
|emptyBtnText|清空按钮|String|-|清空|
|printBtnText|打印按钮|String|-|打印|
|excelBtnText|导出按钮|String|-|导出|


## Search Option Attributes
|参数|说明|类型|可选值|默认值|
|------------------|--------------------------------------------------------------------------------------------|----------------------------|------------|------|
|searchShow|首次加载是否显示搜索|Boolean|true/false|true|
|searchEnter|回车提交表单|Boolean|true/false|true|
|searchIcon|是否展示半收缩按钮|Boolean|true/false|true|
|searchIndex|展示半收缩按钮的个数|Number|-|2|


## Search Column Attributes

|参数|说明|类型|可选值|默认值|
|------------------|--------------------------------------------------------------------------------------------|----------------------------|------------|------|
|searchValue|搜索表单的默认值|Number/String|-|-|
|searchPlaceholder|搜索框的辅助文字|String|-|label|
|searchTipPlacement|搜索文字提示展示方向|String|top-start/top/top-end/left-start/left-end/right-start/right/right-end/bottom-start/bottom/bottom-end|-|
|searchTip|弹窗编辑文字提示|String|-|-|
|searchSpan|搜索框栅列|Number|-|8|
|searchSize|搜索框大小|String|-|small|
|searchOrder|搜索排序|Number|-|-|
|searchGutter|搜索框的间距|String|-|20|
|searchRange|范围搜索|Boolean|true/false|false|
|searchLabelWidth|搜索框的文字宽度|Number|-|80|
|searchClearable|搜索框的清除按钮|Boolean|true/false|false|
|searchMultiple|搜索表单的是否多选|Boolean|true/false|false|
|searchFilterable|是否可以输入搜索。|Boolean|true/false|false|
|searchFilterMethod|数据过滤使用的方法，如果是多选的筛选项，对每一条数据会执行多次，任意一次返回true就会显示。|Function(value,row,column)|-|-|


## Page Attributes

|参数|说明|类型|可选值|默认值|
|----------------|-----------------------|--------------------|------------------|---------------------|
|total|总条数,如果为0的话不显示分页|Number|-|0|
|currentPage|当前页码|Number|-|1|
|background|分页背景|Boolean|true/false|true|
|pageSize|每页显示多少条|Number|—|—|
|pageSizes|分页的数组分段|Array|—|[10,20,30,50,100]|
|pagerCount|多少页后中间隐藏|Number|-|5|

## Events

|事件名|说明|参数|
|------------------|---------------------------|-------------------------|
|current-change|切换页面时触发该事件|page|
|current-row-change|当表格的当前行发生变化的时候会触发该事件，如果要高亮当前行，请打开表格的highlightCurrentRow属性为true|currentRow,oldCurrentRow|
|select|单个选择回调|selection, row|
|selectAll|勾选全选|selection|
|date-change|表格日期回调方法|date|
|filter-change|过滤回调函数|params|
|cell-mouse-enter|当单元格 hover 进入时会触发该事件|row, column, cell, event|
|cell-mouse-leave|当单元格 hover 退出时会触发该事件|row, column, cell, event|
|cell-click|当某个单元格被点击时会触发该事件|row, column, cell, event|
|cell-dblclick|当某个单元格被双击击时会触发该事件|row, column, cell, event|
|row-update|编辑数据后确定触发该事件|row,index,done,loading|
|row-save|新增数据后点击确定触发该事件|row,done,loading|
|row-del|行数据删除时触发该事件|row,index|
|row-click|当某一行被点击时会触发该事件|row,event,column|
|row-dblclick|当某一行被双击时会触发该事件|row,column|
|refresh-change|点击刷新按钮触发该事件|page|
|size-change|页面每页显示的条数触发该事件|pageSize|
|sort-change|调用排序后触发该事件|list|
|search-change|点击搜索后触发该事件|params,done|
|search-reset|清空搜索回调方法|-|
|selection-change|当选择项发生变化时会触发该事件|selection|
|toggleRowExpansion|用于可展开表格，切换某一行的展开状态，如果使用了第二个参数，则是设置这一行展开与否（expanded 为 true 则展开|row, expanded|

## Methods

|方法名|说明|参数|
|---------------|------------------------------------------------------------------------------------|----------|
|clearValidate|清空表格中表单验证。|
|rowAdd|打开表单新增窗口||
|getPropRef|获取prop的ref对象|prop|
|rowSave|表单保存调用||
|rowUpdate|表单更新调用||
|rowView|打开表单查看窗口|row,index|
|rowEdit|打开表单编辑窗口|row,index|
|rowCell|打开行编辑|row,index|
|rowPrint|打印表格||
|rowExcel|导出表格||
|resetForm|清空表单数据||
|setCurrentRow|用于单选表格，设定某一行为选中行，如果调用时不加参数，则会取消目前高亮行的选中状态。|row|
|selectClear|用于多选表格，清空用户的选择。||
|searchReset|清空搜索栏目的值||
|toggleSelection|用于多选表格，切换所有行的选中状态。||
|handleLoadDic|用于 dicUrl重新获取数据||
## Scoped Slot

|name|说明|
|---|-----|
|列的名称|列自定义列的内容，参数为{row,label,dic,$index}|
|列表单的名称+Form(nameForm)|表单自定义列的内容，参数为{row,label,dic,$index}|
|列表单的名称+Type(nameType)|表单自定义列的内容，参数为{row,label,value}|
|empty|暂无数据的自定义卡槽|
|search|搜索自定义卡槽|
|searchMenu|搜索按钮自定义卡槽|
|expand|折叠板的自定义内容,参数为{row,label,dic,$index}|
|menu|菜单的操作按钮自定义内容,参数为{row,label,dic,$index}|
|menuForm|表单操作按钮的自定义内容,参数为{row,label,dic,$index}|
|menuLeft|表格头部左侧内容|
|menuRight|表格头部右侧内容|
|menuBtn|操作栏目下拉菜单自定义(要用el-dropdown-item组件包裹起来),参数为{row,label,dic,$index}|
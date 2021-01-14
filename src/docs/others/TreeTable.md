# TreeTable 左树右表
----
- 在element-ui的tree，form，table等组件的基础上，根据业务需求，可以直接使用于页面，亦可通过弹窗显示，可以设置单选或多选模式

### 基本用法（单选）

<div class="demo-block">
    <bee-tree-table
        :column="column"
        :treeData="treeData"
        :curdData="curdData"
        :page.sync="page"
        :width="280"
        @node-click="handleTreeNode"
        @current-row="handleCurrentRow"
        @crud-load="handleCrudLoad"
        @search="handleSearch"
    ></bee-tree-table>
</div>
<script>
import { Message, Notification } from "element-ui";
const staffData = [
    { id: '1', name: '用户 1', code: '123123', post: '前端开发', dept: '技术部' },
    { id: '2', name: '用户 2', code: '123123', post: '前端开发', dept: '技术部2'  },
    { id: '3', name: '用户 3', code: '123123', post: '前端开发', dept: '技术部3'  },
    { id: '4', name: '用户 4', code: '123123', post: '前端开发', dept: '技术部4'  }
]
export default {
    data() {
        return {
            box1: false,
            box2: false,
            page: {
                pageSize: 20,
                pagerCount: 5,
            },
            column: [
                {
                    label: "员工姓名",
                    prop: "name",
                },
                {
                    label: "工号",
                    prop: "code",
                },
                {
                    label: "部门",
                    prop: "dept",
                },
                {
                    label: "岗位",
                    prop: "post",
                },
            ],
            treeData: [
                {
                    value: 0,
                    label: "一级部门",
                    children: [
                        {
                            value: 1,
                            label: "一级部门1",
                        },
                        {
                            value: 2,
                            label: "一级部门2",
                        },
                        {
                            value: 3,
                            label: "一级部门3",
                        },
                        {
                            value: 4,
                            label: "一级部门4",
                        },
                    ],
                },
            ],
            curdData: [],
            props: {
                label: 'name'
            }
        };
    },
    mounted() {
        this.loadCrudData()
    },
    methods: {
        handleDialog(type) {
            type ? (this.box2 = true) : (this.box1 = true);
        },
        loadCrudData() {
            this.$nextTick(()=> {
                setTimeout(()=> {
                    this.curdData = staffData;
                    this.page.total = 30;
                }, 500)
            })
        },
        handleCrudLoad(page) {
            this.page.currentPage = page.currentPage
            this.loadCrudData()
        },
        handleTreeNode(data) {// 左树节点点击事件
            Message.success(JSON.stringify(data));
        },
        handleCurrentRow(val) {// 表格行单击
            Notification({
                showClose: true,
                message: "单选" + JSON.stringify(val),
                type: "success",
            });
        },
        handleSearch(params) { // 查询
            Notification({
                showClose: true,
                message: "查询结果" + JSON.stringify(params),
                type: "success",
            });
        },
        handleCloseTag(data) { // 关闭标签
            Message.success(JSON.stringify(data));
        }
    },
};
</script>

:::demo
```html
<div class="demo-block">
    <bee-tree-table
        :column="column"
        :treeData="treeData"
        :curdData="curdData"
        :page.sync="page"
        :width="280"
        @node-click="handleTreeNode"
        @current-row="handleCurrentRow"
        @crud-load="handleCrudLoad"
        @search="handleSearch"
    ></bee-tree-table>
</div>
<script>
import { Message, Notification } from "element-ui";
const staffData = [
    { id: '1', name: '用户 1', code: '123123', post: '前端开发', dept: '技术部' },
    { id: '2', name: '用户 2', code: '123123', post: '前端开发', dept: '技术部2'  },
    { id: '3', name: '用户 3', code: '123123', post: '前端开发', dept: '技术部3'  },
    { id: '4', name: '用户 4', code: '123123', post: '前端开发', dept: '技术部4'  }
]
export default {
    data() {
        return {
            box1: false,
            box2: false,
            page: {
                pageSize: 20,
                pagerCount: 5,
            },
            column: [
                {
                    label: "员工姓名",
                    prop: "name",
                },
                {
                    label: "工号",
                    prop: "code",
                },
                {
                    label: "部门",
                    prop: "dept",
                },
                {
                    label: "岗位",
                    prop: "post",
                },
            ],
            treeData: [
                {
                    value: 0,
                    label: "一级部门",
                    children: [
                        {
                            value: 1,
                            label: "一级部门1",
                        },
                        {
                            value: 2,
                            label: "一级部门2",
                        },
                        {
                            value: 3,
                            label: "一级部门3",
                        },
                        {
                            value: 4,
                            label: "一级部门4",
                        },
                    ],
                },
            ],
            curdData: [],
            props: {
                label: 'name'
            }
        };
    },
    mounted() {
        this.loadCrudData()
    },
    methods: {
        handleDialog(type) {
            type ? (this.box2 = true) : (this.box1 = true);
        },
        loadCrudData() {
            this.$nextTick(()=> {
                setTimeout(()=> {
                    this.curdData = staffData;
                    this.page.total = 30;
                }, 500)
            })
        },
        handleCrudLoad(page) {
            this.page.currentPage = page.currentPage
            this.loadCrudData()
        },
        handleTreeNode(data) {// 左树节点点击事件
            Message.success(JSON.stringify(data));
        },
        handleCurrentRow(val) {// 表格行单击
            Notification({
                showClose: true,
                message: "单选" + JSON.stringify(val),
                type: "success",
            });
        },
        handleSearch(params) { // 查询
            Notification({
                showClose: true,
                message: "查询结果" + JSON.stringify(params),
                type: "success",
            });
        },
        handleCloseTag(data) { // 关闭标签
            Message.success(JSON.stringify(data));
        }
    },
};
</script>

```
:::


### 多选
<div class="demo-block">
    <bee-tree-table
        :column="column"
        :treeData="treeData"
        :curdData="curdData"
        :multiple="true"
        :valProps="props"
        :page.sync="page"
        :width="300"
        placeholder="请输入员工姓名或员工号"
        @node-click="handleTreeNode"
        @crud-load="handleCrudLoad"
        @search="handleSearch"
        @close-tag="handleCloseTag"
    >
    </bee-tree-table>
</div>

:::demo
```html

<bee-tree-table
    :column="column"
    :treeData="treeData"
    :curdData="curdData"
    :multiple="true"
    :valProps="props"
    :page.sync="page"
    :width="300"
    placeholder="请输入员工姓名或员工号"
    @node-click="handleTreeNode"
    @crud-load="handleCrudLoad"
    @search="handleSearch"
    @close-tag="handleCloseTag"
>
</bee-tree-table>

```
脚本部分与基础用法共用
```

```
:::


### 弹窗

<div class="demo-block">
    <el-button @click="handleDialog(0)">弹框单选</el-button>
    <el-dialog
        title="员工选择"
        :visible.sync="box1"
        v-dialogdrag
        class="bee-dialog"
        width="60%"
        top="8vh"
    >
        <div style="height: 65vh; overflow: auto">
            <bee-tree-table
                :column="column"
                :treeData="treeData"
                :curdData="curdData"
                :page.sync="page"
                :width="280"
                @node-click="handleTreeNode"
                @current-row="handleCurrentRow"
                @crud-load="handleCrudLoad"
                @search="handleSearch"
            ></bee-tree-table>
        </div>
        <span slot="footer" class="dialog-footer">
            <el-button @click="box = false">取 消</el-button>
            <el-button type="primary" @click="box = false">确 定</el-button>
        </span>
    </el-dialog>
    &nbsp;&nbsp;
    <el-button @click="handleDialog(1)">弹框多选</el-button>
    <el-dialog
        title="员工选择"
        :visible.sync="box2"
        v-dialogdrag
        class="bee-dialog"
        width="60%"
        top="8vh"
    >
        <div style="height: 65vh; overflow: auto">
            <bee-tree-table
                :column="column"
                :treeData="treeData"
                :curdData="curdData"
                :multiple="true"
                :valProps="props"
                :page.sync="page"
                :width="300"
                placeholder="请输入员工姓名或员工号"
                @node-click="handleTreeNode"
                @crud-load="handleCrudLoad"
                @search="handleSearch"
                @close-tag="handleCloseTag"
            >
            </bee-tree-table>
        </div>
        <span slot="footer" class="dialog-footer">
            <el-button @click="box = false">取 消</el-button>
            <el-button type="primary" @click="box = false">确 定</el-button>
        </span>
    </el-dialog>
</div>

:::demo
```html

<el-button @click="handleDialog(0)">弹框单选</el-button>
<el-dialog
    title="员工选择"
    :visible.sync="box1"
    v-dialogdrag
    class="bee-dialog"
    width="60%"
    top="8vh"
>
    <div style="height: 65vh; overflow: auto">
        <bee-tree-table
            :column="column"
            :treeData="treeData"
            :curdData="curdData"
            :page.sync="page"
            :width="280"
            @node-click="handleTreeNode"
            @current-row="handleCurrentRow"
            @crud-load="handleCrudLoad"
            @search="handleSearch"
        ></bee-tree-table>
    </div>
    <span slot="footer" class="dialog-footer">
        <el-button @click="box = false">取 消</el-button>
        <el-button type="primary" @click="box = false">确 定</el-button>
    </span>
</el-dialog>

<el-button @click="handleDialog(1)">弹框多选</el-button>
<el-dialog
    title="员工选择"
    :visible.sync="box2"
    v-dialogdrag
    class="bee-dialog"
    width="60%"
    top="8vh"
>
    <div style="height: 65vh; overflow: auto">
        <bee-tree-table
            :column="column"
            :treeData="treeData"
            :curdData="curdData"
            :multiple="true"
            :valProps="props"
            :page.sync="page"
            :width="300"
            placeholder="请输入员工姓名或员工号"
            @node-click="handleTreeNode"
            @crud-load="handleCrudLoad"
            @search="handleSearch"
            @close-tag="handleCloseTag"
        >
        </bee-tree-table>
    </div>
    <span slot="footer" class="dialog-footer">
        <el-button @click="box = false">取 消</el-button>
        <el-button type="primary" @click="box = false">确 定</el-button>
    </span>
</el-dialog>
```
脚本部分与基础用法共用
```

```
:::


## Props
|参数|说明|类型|可选值|默认值|
|----------------------|--------------------------------|:--------:|:------------:|:------:|
|treeData|左树数据|Array|—|—|
|curdData|右表数据|Array|—|—|
|column|右表属性|Array|—|—|
|width|左树显示宽度|String|-|220|
|placeholder|查询提示语|String|'pithy'/'rich'/'info'|'pithy'|
|multiple|是否多选|Boolean|true/false|true|
|page|翻页设置|Object|—|{pageSize: 20,pagerCount: 5}|
|valProps|选中值属性配置，多选时使用|Object|—|{label: 'label',value: 'value'}|

## Events

|事件名|说明|参数|
|----------------------|--------|:------------:|
|crud-load|右表初始化加载或翻页加载调用|page|
|node-click|左树节点点击事件，返回节点对象|data|
|current-row|右表表格行点击事件，返回行对象|val|
|search|查询事件回调|params|
|close-tag|删除已选内容，返回对象索引|index|

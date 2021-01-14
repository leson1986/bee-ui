# HighTimeline 高级时间线 
----
- 在element-ui的时间线基础上，根据业务需求，封装了三种样式，可以根据不同需求使用，可用于流程信息展示，基础信息表展示等情形

### 基本用法（简洁版本）

<div class="demo-block">
    <bee-high-timeline :flow-data="activityData" skin="pithy" :flow-props="flowLineProps" :flow-color="flowColor"></bee-high-timeline>
</div>
<script>
export default {
    data() {
        return {
                activityInfoData: [
                    {
                        endTime: '2010-12-08',
                        startTime: '2010-10-08',
                        mainText: "金融学",
                        statusMainText: "全日制",
                        otherMainText: "本科",
                        subMainText: "广东金金融学院",
                        subStatusMainText: "本科",
                    },
                    {
                        endTime: '2010-12-08',
                        startTime: '2010-10-08',
                        mainText: "法学",
                        statusMainText: "全日制",
                        otherMainText: "本科",
                        subMainText: "中国法律大学",
                        subStatusMainText: "本科",
                    },
                ],
                activityData: [
                    {
                        status: 'APPROVAL',
                        statusText: '待审批',
                        tenantDepartmentName: '部门名称',
                        tenantName: '',
                        comment: '详情详情请查详情请查',
                        name: '主管',
                        assigneeName: '马云',
                        endTime: '2020-10-10',
                        statusFlag: '启动',
                        flowId: '9900088773',
                        flowTxt: '转正流程',
                        subFlowTxt: '自评',
                        startTime: '2010-10-08'
                    },
                    {
                        status: 'TURN_TO_DO',
                        statusText: '通过',
                        tenantDepartmentName: '人力资源部',
                        tenantName: '李响1',
                        comment: '',
                        name: '主管主管主管主管主管主管',
                        assigneeName: '马云',
                        endTime: '2020-10-10',
                        statusFlag: '转办',
                    },
                    {
                        status: 'PASSED',
                        statusText: '通过',
                        tenantDepartmentName: '人力资源部',
                        tenantName: '李响',
                        comment: '',
                        name: '主管主管主管主管主管主管',
                        assigneeName: '马云',
                        endTime: '2020-10-10',
                        statusFlag: '沟通',
                        subTask: [
                            {
                                status: 'COMMUNICATION',
                                statusText: '沟通',
                                tenantDepartmentName: '人力资源部',
                                tenantName: '李连杰',
                                comment: '沟通沟通沟通沟通沟通沟通沟通沟通',
                                name: '主管主管主管主管主管主管主管',
                                assigneeName: '马云马云马云',
                                endTime: '2020-10-10',
                            }
                        ]
                    }
                ], // 流程信息
                flowLineProps: {
                    status: 'status',
                    statusText: 'statusText',
                    department: 'tenantDepartmentName',
                    info: 'comment',
                    post: 'name',
                    time: 'endTime',
                    tenant: 'tenantName',
                    assignee: 'assigneeName',
                    subTask: 'subTask',
                    flowText: 'flowTxt',
                    subFlowText: 'subFlowTxt',
                },
                flowColor: {
                    'SUBMITTED': '#1890FF',
                    'APPROVAL': '#000000',
                    'COMMUNICATION': '#29AFB8',
                    'REPLY': '#1890FF',
                    'WAIT_REPLY': '#FAAD14',
                    'CANCEL_COMMUNICATION': '#F5222D',
                    'TODO': '#8C8C8C',
                    'WITHDRAW': '#F5222D',
                    'PASSED': '#52C41A',
                    'TURN_TO_DO': '#1890FF',
                    'INVALID': '#F5222D',
                    'ABANDONED': '#F5222D'
                }
            }
    }
};
</script>

:::demo
```html

<div class="demo-block">
    <bee-high-timeline :flow-data="activityData" skin="pithy" :flow-props="flowLineProps" :flow-color="flowColor"></bee-high-timeline>
</div>
<script>
export default {
    data() {
        return {
                activityInfoData: [
                    {
                        endTime: '2010-12-08',
                        startTime: '2010-10-08',
                        mainText: "金融学",
                        statusMainText: "全日制",
                        otherMainText: "本科",
                        subMainText: "广东金金融学院",
                        subStatusMainText: "本科",
                    },
                    {
                        endTime: '2010-12-08',
                        startTime: '2010-10-08',
                        mainText: "法学",
                        statusMainText: "全日制",
                        otherMainText: "本科",
                        subMainText: "中国法律大学",
                        subStatusMainText: "本科",
                    },
                ],
                activityData: [
                    {
                        status: 'APPROVAL',
                        statusText: '待审批',
                        tenantDepartmentName: '部门名称',
                        tenantName: '',
                        comment: '详情详情请查详情请查',
                        name: '主管',
                        assigneeName: '马云',
                        endTime: '2020-10-10',
                        statusFlag: '启动',
                        flowId: '9900088773',
                        flowTxt: '转正流程',
                        subFlowTxt: '自评',
                        startTime: '2010-10-08'
                    },
                    {
                        status: 'TURN_TO_DO',
                        statusText: '通过',
                        tenantDepartmentName: '人力资源部',
                        tenantName: '李响1',
                        comment: '',
                        name: '主管主管主管主管主管主管',
                        assigneeName: '马云',
                        endTime: '2020-10-10',
                        statusFlag: '转办',
                    },
                    {
                        status: 'PASSED',
                        statusText: '通过',
                        tenantDepartmentName: '人力资源部',
                        tenantName: '李响',
                        comment: '',
                        name: '主管主管主管主管主管主管',
                        assigneeName: '马云',
                        endTime: '2020-10-10',
                        statusFlag: '沟通',
                        subTask: [
                            {
                                status: 'COMMUNICATION',
                                statusText: '沟通',
                                tenantDepartmentName: '人力资源部',
                                tenantName: '李连杰',
                                comment: '沟通沟通沟通沟通沟通沟通沟通沟通',
                                name: '主管主管主管主管主管主管主管',
                                assigneeName: '马云马云马云',
                                endTime: '2020-10-10',
                            }
                        ]
                    }
                ], // 流程信息
                flowLineProps: {
                    status: 'status',
                    statusText: 'statusText',
                    department: 'tenantDepartmentName',
                    info: 'comment',
                    post: 'name',
                    time: 'endTime',
                    tenant: 'tenantName',
                    assignee: 'assigneeName',
                    subTask: 'subTask',
                    flowText: 'flowTxt',
                    subFlowText: 'subFlowTxt',
                },
                flowColor: {
                    'SUBMITTED': '#1890FF',
                    'APPROVAL': '#000000',
                    'COMMUNICATION': '#29AFB8',
                    'REPLY': '#1890FF',
                    'WAIT_REPLY': '#FAAD14',
                    'CANCEL_COMMUNICATION': '#F5222D',
                    'TODO': '#8C8C8C',
                    'WITHDRAW': '#F5222D',
                    'PASSED': '#52C41A',
                    'TURN_TO_DO': '#1890FF',
                    'INVALID': '#F5222D',
                    'ABANDONED': '#F5222D'
                }
            }
    }
};
</script>

```
:::


### 多彩版本

<div class="demo-block">
    <bee-high-timeline :flow-data="activityData" skin="rich" :flow-props="flowLineProps" :flow-color="flowColor"></bee-high-timeline>
</div>

:::demo
```html

<bee-high-timeline :flow-data="activityData" skin="rich" :flow-props="flowLineProps" :flow-color="flowColor"></bee-high-timeline>

```
脚本部分与基础用法共用
```

```
:::


### 信息版本

<div class="demo-block">
    <bee-high-timeline :flow-data="activityInfoData" skin="info" :flow-props="flowLineProps">
        <template slot="other" slot-scope="scope">
            <div>
                <i
                    @click="handelDetails(scope)"
                    title="查看详情"
                    class="el-icon-tickets link-pointer"
                    style="color: #1890FF;margin-right: 20px"
                >
                </i>
                <i
                    @click="handleEdit(scope)"
                    title="编辑详情"
                    class="el-icon-edit link-pointer"
                    style="color: #1890FF;"
                >
                </i>
            </div>
        </template>
    </bee-high-timeline>
</div>

:::demo
```html
<bee-high-timeline :flow-data="activityInfoData" skin="info" :flow-props="flowLineProps">
    <template slot="other" slot-scope="scope">
        <div>
            <i
                @click="handelDetails(scope)"
                title="查看详情"
                class="el-icon-tickets link-pointer"
                style="color: #1890FF;margin-right: 20px"
            >
            </i>
            <i
                @click="handleEdit(scope)"
                title="编辑详情"
                class="el-icon-edit link-pointer"
                style="color: #1890FF;"
            >
            </i>
        </div>
    </template>
</bee-high-timeline>

```
脚本部分与基础用法共用
```

```
:::

## Props
|参数|说明|类型|可选值|默认值|
|----------------------|--------------------------------|:--------:|:------------:|:------:|
|flowData|数据|Array|—|—|
|skin|皮肤|String| pithy(简洁) / rich(多彩) / info(信息) | pithy |
|header|显示头部信息，rich特供|Boolean| true / false |true|
|defaultProps|默认属性,主要为信息对象属性,如果属性相同可不配置,反之,必须配置|Object|—|见defaultProps|
|flowColor|节点颜色,根据状态配置相关颜色|Obejct|—|见flowColor|

## DefaultProps

|参数|说明|类型|可选值|默认值|
|----------------------|--------------------------------|:--------:|:------------:|:------:|
|status|状态code|String|—|—|
|statusText|状态文本|String|—|—|
|department|部门名称|String|—|—|
|info|审批详情|String|—|—|
|post|岗位|String|—|—|
|time|最后审批时间|Date|—|—|
|tenant|被指定操作者|String|—|—|
|assignee|审批人姓名|String|—|—|
|subTask|子任务流程信息，“pithy”特供|Array|—|—|
|statusFlag|状态标识（发起流程的原因），"rich"特供|String|—|—|
|startTime|提交申请时间，"rich"特供|Date|—|—|
|flowId|流程ID，"rich"特供|Array|—|—|
|flowText|主流程文本，"rich"特供|Array|—|—|
|subFlowText|子流程文本，"rich"特供|Array|—|—|
|mainText|状态文本，"info"特供|String|—|—|
|statusMainText|状态文本，"info"特供|String|—|—|
|otherMainText|状态文本，"info"特供|String|—|—|
|subMainText|状态文本，"info"特供|String|—|—|
|subStatusMainText|状态文本，"info"特供|String|—|—|


## flowColor
|参数|说明|类型|可选值|默认值|
|----------------------|--------------------------------|:--------:|:------------:|:------:|
|SUBMITTED|状态code|String|—|'#1890FF'|
|APPROVAL|状态code|String|—|'#FAAD14'|
|COMMUNICATION|状态code|String|—|'#29AFB8'|
|REPLY|状态code|String|—|'#1890FF'|
|WAIT_REPLY|状态code|String|—|'#FAAD14'|
|CANCEL_COMMUNICATION|状态code|String|—|'#F5222D'|
|TODO|状态code|String|—|'#8C8C8C'|
|WITHDRAW|状态code|String|—|'#F5222D'|
|PASSED|状态code|String|—|'#52C41A'|
|TURN_TO_DO|状态code|String|—|'#1890FF'|
|INVALID|状态code|String|—|'#F5222D'|
|ABANDONED|状态code|String|—|'#F5222D'|










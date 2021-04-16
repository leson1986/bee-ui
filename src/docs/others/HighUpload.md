<script>
export default {
    data() {
        return {
            upload: {
                isDetail1: false, //是否显示上传
                isDetail2: true, //是否显示上传
                downloadUrl: "https://files-cdn.cnblogs.com/files/yocichen/", // 下载URL
                action: "", //请求URL
                autoUpload: true, //是否自动上传
                limit: 5, //限制上传的个数
                multiple: false, //是否批量上传
                size: 10, //限制图片大小 单位为M
                title: "上传附件", //提示标题
                accept:
                    ".doc,.docx,.xls,.xlsx,.csv,.pdf,.ppt,.pptx,.jpg,.jpeg,.png", //支持上传的格式
                uploadType: "normal", //上传的类型，‘normal’单个或批量上传，‘table’表格文件上传
                fileList: [
                    {
                        url:
                            "group1/M00/00/4F/wKgAy2BLIGSAW-bXAAANMvQaeGk983.png",
                        name: "操作指南1.png",
                        size: "2033.kb",
                        response: 1,
                    },
                    {
                        url:
                            "group1/M00/00/4F/wKgAy2BLIGSAW-bXAAANMvQaeGk983.png",
                        name: "操作指南2.png",
                        size: "20313.kb",
                        response: 2,
                    },
                ],
            },
        }
    }
}
</script>

# HighUpload 高级上传组件 
----
- 在element-ui的时间线基础上，根据业务需求，可单传，多传

### 基本用法（上传）

<div class="demo-block">
    <bee-high-upload
        v-model="upload.fileList"
        :limit="upload.limit"
        :multiple="upload.multiple"
        :size="upload.size"
        :title="upload.title"
        :isDetail="upload.isDetail1"
        :uploadType="upload.uploadType"
        :action="upload.action"
        :autoUpload="upload.autoUpload"
        :accept="upload.accept"
    ></bee-high-upload>
</div>


:::demo
```html

<div class="demo-block">
    <bee-high-upload
        v-model="upload.fileList"
        :limit="upload.limit"
        :multiple="upload.multiple"
        :size="upload.size"
        :title="upload.title"
        :isDetail="upload.isDetail1"
        :uploadType="upload.uploadType"
        :action="upload.action"
        :autoUpload="upload.autoUpload"
        :accept="upload.accept"
    ></bee-high-upload>
</div>
<script>
export default {
    data() {
        return {
            upload: {
                isDetail1: false, //是否显示上传
                downloadUrl: "https://files-cdn.cnblogs.com/files/yocichen/", // 下载URL
                action: "", //请求URL
                autoUpload: true, //是否自动上传
                limit: 5, //限制上传的个数
                multiple: false, //是否批量上传
                size: 10, //限制图片大小 单位为M
                title: "上传附件", //提示标题
                accept:
                    ".doc,.docx,.xls,.xlsx,.csv,.pdf,.ppt,.pptx,.jpg,.jpeg,.png", //支持上传的格式
                uploadType: "normal", //上传的类型，‘normal’单个或批量上传，‘table’表格文件上传
                fileList: [
                    {
                        url:
                            "group1/M00/00/4F/wKgAy2BLIGSAW-bXAAANMvQaeGk983.png",
                        name: "操作指南1.png",
                        size: "2033.kb",
                        response: 1,
                    },
                    {
                        url:
                            "group1/M00/00/4F/wKgAy2BLIGSAW-bXAAANMvQaeGk983.png",
                        name: "操作指南2.png",
                        size: "2033.kb",
                        response: 2,
                    },
                ],
            },
        }
    }
}
</script>

```
:::


### 显示详情

<div class="demo-block">
    <bee-high-upload
        v-model="upload.fileList"
        :limit="upload.limit"
        :multiple="upload.multiple"
        :size="upload.size"
        :title="upload.title"
        :isDetail="upload.isDetail2"
        :uploadType="upload.uploadType"
        :downloadUrl="upload.downloadUrl"
        :action="upload.action"
        :autoUpload="upload.autoUpload"
        :accept="upload.accept"
    ></bee-high-upload>
</div>


:::demo
```html

<div class="demo-block">
    <bee-high-upload
        v-model="upload.fileList"
        :limit="upload.limit"
        :multiple="upload.multiple"
        :size="upload.size"
        :title="upload.title"
        :isDetail="upload.isDetail1"
        :uploadType="upload.uploadType"
        :action="upload.action"
        :autoUpload="upload.autoUpload"
        :accept="upload.accept"
    ></bee-high-upload>
</div>
<script>
export default {
    data() {
        return {
            upload: {
                isDetail2: true, //是否显示上传
                downloadUrl: "https://files-cdn.cnblogs.com/files/yocichen/", // 下载URL
                action: "", //请求URL
                autoUpload: true, //是否自动上传
                limit: 5, //限制上传的个数
                multiple: false, //是否批量上传
                size: 10, //限制图片大小 单位为M
                title: "上传附件", //提示标题
                accept:
                    ".doc,.docx,.xls,.xlsx,.csv,.pdf,.ppt,.pptx,.jpg,.jpeg,.png", //支持上传的格式
                uploadType: "normal", //上传的类型，‘normal’单个或批量上传，‘table’表格文件上传
                fileList: [
                    {
                        url:
                            "group1/M00/00/4F/wKgAy2BLIGSAW-bXAAANMvQaeGk983.png",
                        name: "操作指南1.png",
                        size: "2033.kb",
                        response: 1,
                    },
                    {
                        url:
                            "group1/M00/00/4F/wKgAy2BLIGSAW-bXAAANMvQaeGk983.png",
                        name: "操作指南2.png",
                        size: "2033.kb",
                        response: 2,
                    },
                ],
            },
        }
    }
}
</script>

```
:::


## Props
|参数|说明|类型|可选值|默认值|
|----------------------|--------------------------------|:--------:|:------------:|:------:|
|uploadType|上传的类型，‘normal’单个或批量上传，‘table’表格文件上传|String|normal / table|normal|
|action|请求url|String|||
|autoUpload|是否自动上传|Boolean|false / true| true |
|isDetail|是否显示上传|Boolean|false / true| false |
|accept|支持的文件格式 例："image/gif,image/jpeg"|String||.doc,.docx,.xls,.xlsx,.csv,.pdf,.ppt,.pptx,.jpg,.jpeg,.png|
|limit|限制上传的个数|Number|1-无穷大|3|
|multiple|是否能批量上传|Boolean|false / true| true |
|token|token|String|||
|size|限制图片上传的大小|Number|| 10 |
|title|提示标题|String|| 上传附件 |
|value|绑定值|Array|| [] |









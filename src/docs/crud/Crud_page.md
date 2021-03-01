<script>
  export default {
    data() {
      return {
        page1: {
          currentPage: 1,
          total: 0,
          layout: "total,pager,prev, next",
          background:false,
          pageSize: 10
        },
        page: {
           pageSize: 20,
           pagerCount:5
        },
        data: [],
        option:{
          align:'center',
          menuAlign:'center',
          column:[
             {
              label:'姓名',
              prop:'name'
            }, {
              label:'性别',
              prop:'sex'
            }
          ]
        },
      };
    },
    created(){
      this.getList()
    },
    methods: {
      getList(){
        this.page1.total=40;
        if(this.page1.currentPage===1){
          this.data=[{
            name:'张三',
            sex:'男'
          }]
        }else if(this.page1.currentPage==2){
          this.data=[{
            name:'李四',
            sex:'女'
          }]
        }
      },
      onLoad(page){
        this.$message.success('分页信息:'+JSON.stringify(page));
        this.page.total=40;
        //模拟分页
        if (this.page.currentPage === 1) {
          this.data = [
            {
              id:1,
              name: '张三',
              sex: '男'
            },{
              id:2,
              name: '李四',
              sex: '女'
            }
          ]
        } else if (this.page.currentPage == 2) {
          this.data = [
            {
              id:3,
              name: '王五',
              sex: '女'
            },{
              id:4,
              name: '赵六',
              sex: '女'
            }
          ]
        }
      },
      sizeChange(val){
        this.page1.currentPage=1;
        this.page1.pageSize=val;
        this.getList();
        this.$message.success('行数'+ val);
      },
      currentChange(val){
        this.page1.currentPage=val;
        this.getList();
        this.$message.success('页码'+val);
      },
    }
  };
</script>


# 分页


## 普通用法

<div class="demo-block">
<div class="demo-code">
{{page}}
</div>
<bee-crud
  :data="data"
  :option="option"
  :page.sync="page"
  @on-load="onLoad"
></bee-crud>
</div>

:::demo 
首次加载调用`on-load`方法加载数据，返回`page`分页对象信息,赋值`page`的`total`总条数即可,如果`total`为0的话，或者`simplePage`为true只有1页的时候，分页选择器会隐藏
```html

{{page}}
<bee-crud
  :data="data"
  :option="option"
  :page.sync="page"
  @on-load="onLoad"
></bee-crud>

<script>
  export default {
    data() {
      return {
        page: {
          pageSize: 20,
          pagerCount:5
        },
        data: [],
        option: {
          align: 'center',
          menuAlign: 'center',
          column: [
            {
              label: '姓名',
              prop: 'name'
            },
            {
              label: '性别',
              prop: 'sex'
            }
          ]
        }
      }
    },
    methods: {
      onLoad(page) {
        this.$message.success('分页信息:' + JSON.stringify(page))
        this.page.total = 40
        //模拟分页
        if (this.page.currentPage === 1) {
          this.data = [
            {
              id:1,
              name: '张三',
              sex: '男'
            },{
              id:2,
              name: '李四',
              sex: '女'
            }
          ]
        } else if (this.page.currentPage == 2) {
          this.data = [
            {
              id:3,
              name: '王五',
              sex: '女'
            },{
              id:4,
              name: '赵六',
              sex: '女'
            }
          ]
        }
      }
    }
  }
</script>
```

:::

## 自定义分页

<div class="demo-block">
<div class="demo-code">
{{page1}}
</div>
<bee-crud
  :data="data"
  :option="option"
  :page.sync="page1"
  @size-change="sizeChange"
  @current-change="currentChange"
></bee-crud>
</div>

:::demo 
实际的用法要后台配置，将后台返回值赋值给 page 中的属性， `page`就是分页对象注入，page 对象中的`total`为总页数，`pageSizes`为分页信息，`currentPage`为当前第几页，`pageSize`每一页加载多少条数据，点击页码会调用`current-change`方法回调当前页数，返回当前第几页，点击每页多少条会调`size-change`方法回调

```html
{{page1}}
<bee-crud
  :data="data"
  :option="option"
  :page.sync="page1"
  @size-change="sizeChange"
  @current-change="currentChange"
></bee-crud>

<script>
  export default {
    data() {
      return {
        page1: {
          currentPage: 1,
          total: 0,
          layout: "total,pager,prev, next",
          background:false,
          pageSize: 10
        },
        data: [],
        option: {
          align: 'center',
          menuAlign: 'center',
          column: [
            {
              label: '姓名',
              prop: 'name'
            },
            {
              label: '性别',
              prop: 'sex'
            }
          ]
        }
      }
    },
    created() {
      this.getList()
    },
    methods: {
      getList() {
        this.page1.total = 40
        if (this.page1.currentPage === 1) {
          this.data = [
            {
              id:1,
              name: '张三',
              sex: '男'
            },{
              id:2,
              name: '李四',
              sex: '女'
            }
          ]
        } else if (this.page1.currentPage == 2) {
          this.data = [
            {
              id:3,
              name: '王五',
              sex: '女'
            },{
              id:4,
              name: '赵六',
              sex: '女'
            }
          ]
        }if (this.page1.currentPage === 1) {
          this.data = [
            {
              id:1,
              name: '张三',
              sex: '男'
            },{
              id:2,
              name: '李四',
              sex: '女'
            }
          ]
        } else if (this.page1.currentPage == 2) {
          this.data = [
            {
              id:3,
              name: '王五',
              sex: '女'
            },{
              id:4,
              name: '赵六',
              sex: '女'
            }
          ]
        }
      },
      sizeChange(val) {
        this.page1.currentPage = 1
        this.page1.pageSize = val
        this.getList()
        this.$message.success('行数' + val)
      },
      currentChange(val) {
        this.page1.currentPage = val
        this.getList()
        this.$message.success('页码' + val)
      }
    }
  }
</script>
```

:::

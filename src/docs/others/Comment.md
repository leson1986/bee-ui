<script>
export default {
  data() {
      return {
        data: {
          avatar: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2F5b0988e595225.cdn.sohucs.com%2Fimages%2F20171201%2F972c41f3df48456aac3ef3e2a79492e4.gif&refer=http%3A%2F%2F5b0988e595225.cdn.sohucs.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=jpeg?sec=1613620698&t=0686328448a335d80f87fc4987ad8ae9',
          author: '某人1',
          body: `<p>那，那是一封写给南部母亲的信。我茫然站在骑楼下，我又看到永远的樱子走到街心。其实雨下得并不大，却是一生一世中最大的一场雨。而那封信是这样写的，年轻的樱子知不知道呢？</p>
            <blockquote>妈：我打算在下个月和樱子结婚。</blockquote>`
        },
        option: {
          props: {
            avatar: 'avatar',
            author: 'author',
            body: 'body'
          }
        }
      }
    }
}
</script>

# Comment 评论
常规的评论组件


<div class="demo-block">

  <bee-comment :option="option" :data="data">
    <i class="el-icon-delete" @click="$message('自定义菜单')"></i>
  </bee-comment>
  <bee-comment :option="option" :data="data" reverse>
   <i class="el-icon-delete" @click="$message('自定义菜单')"></i>
  </bee-comment>
</div>




:::demo 
```html
  <bee-comment :option="option" :data="data">
    <i class="el-icon-delete" @click="$message('自定义菜单')"></i>
  </bee-comment>
  <bee-comment :option="option" :data="data" reverse>
   <i class="el-icon-delete" @click="$message('自定义菜单')"></i>
  </bee-comment>
<script>
export default {
  data() {
      return {
        data: {
          avatar: `https://gimg2.baidu.com/image_search/src=http%3A%2F%2F5b0988e595225.cdn.sohucs.com%2F
          images%2F20171201%2F972c41f3df48456aac3ef3e2a79492e4.gif&refer=http%3A%2F%2F5b0988e595225.cdn.sohucs.com&
          app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=jpeg?sec=1613620698&t=0686328448a335d80f87fc4987ad8ae9`,
          author: '某人',
          body: `<p>那，那是一封写给南部母亲的信。我茫然站在骑楼下，我又看到永远的樱子走到街心。
          其实雨下得并不大，却是一生一世中最大的一场雨。而那封信是这样写的，年轻的樱子知不知道呢？</p>
            <blockquote>妈：我打算在下个月和樱子结婚。</blockquote>`
        },
        option: {
          props: {
            avatar: 'avatar',
            author: 'author',
            body: 'body'
          }
        }
      }
    }
}
</script>
```
:::


## Variables

|参数|说明|类型|可选值|默认值|
|-------------|-------------------------------------------------------------|--------|------|------|
|reverse|是否反转|Boolean|true / false|false|

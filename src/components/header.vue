<!---->
<template>
  <div class="header">
      <div class="logo">
        <img src="../assets/img/beeUi_Big_Logo.png">
      </div>
      <div class="list">
        <div class="list-son" @click="$router.push({ path: '/' })">首页</div>
        <div class="list-son" @click="$router.push({ path: '/giud' })">指南</div>
        <div class="list-son" @click="$router.push({ path: '/basic/input' })">组件</div>
        <div class="list-son" @click="$router.push({ path: '/log/deepclone' })">常用日志</div>
      </div>
  </div>
</template>
<script>
  export default {
    data() {
      return {}
    },
    methods: {},
    computed: {},
    components: {},
    mounted() {

    },
  }
</script>
<style scoped lang="stylus">
  @import "../assets/styl/var.styl"
  .header
    height 80px
    min-width 500px
    line-height 80px
    position fixed
    left 0
    right 0
    z-index 1000
    background $color-primary
    display flex
    justify-content: space-between;
    .logo
      height: 80px;
      display: inline-flex;
      align-items: center;
      padding: 0 40px;
      margin-left: 100px;
      background $color-white
      &>div
        font-size: 35px;
        margin-left: 20px;
        color: $color-white;
      &>img
        height 80px
    .list
      height: 80px;
      display: inline-flex;
      padding-right 30px
      .list-son
        font-size: 18px;
        color: $color-white;
        padding: 0 30px;
        cursor pointer
        &:hover
          background  lighten($color-primary,30%)
</style>

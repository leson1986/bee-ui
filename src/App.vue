<template>
  <div id="app">
    <Header></Header>
    <div class="app-main">
      <div class="app-main-left">
        <Menu></Menu>
      </div>
      <div class="app-main-right">
        <router-view/>
      </div>
    </div>
  </div>
</template>

<script>
  import Menu from './components/menu.vue';
  import Header from './components/header.vue';
export default {
  name: 'App',
  components:{
    Menu,Header
  }
}
</script>

<style lang="stylus">
#app
  .app-main
    display: flex;
    min-width: 1101px;
    margin: 0 auto 50px auto;
    width: 85%;
    .app-main-left
      min-width 230px
      position fixed 
      margin-top 80px
      height 100%
      z-index 999
      left 123px
      overflow hidden
      &:hover 
        overflow scroll
      &::-webkit-scrollbar
        width 4px
      &::-webkit-scrollbar-thumb
        opacity: 0;
        cursor: pointer;
        background-color: rgba(144, 147, 153, 1);
        border-radius: inherit;
      &::-webkit-scrollbar-track
        cursor: pointer;
        background-color: rgba(255, 255, 255, 1);
        border-radius: inherit;
    .app-main-right
      margin-top 80px
      position relative
      padding-top 15px
      flex 1
      padding-left 280px
</style>

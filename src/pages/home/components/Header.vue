<template>
  <div class="header">
    <div class="header-left">
      <span class="iconfont back-icon">&#xe624;</span>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      输入城市/景点/游玩主题
    </div>
    <router-link to='/city'>
      <div class="header-right">
      {{this.city}}
      <span class="iconfont arrow-icon">&#xe64a;</span>
    </div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader',
  props: {
    city: String
  }
}
</script>

<style lang="stylus" scoped>
@import '~@/assets/stylus/varibles.styl'
.header
  display flex
  line-height .86rem
  background-color $bgColor
  color #fff
  .header-left
    width 0.64rem
    float left
    .back-icon
      text-align center
      font-size 0.4rem
  .header-input
    flex 1
    background #fff
    height 0.64rem
    line-height 0.64rem
    margin-left 0.2rem
    margin-top 0.12rem
    padding-left 0.2rem
    border-radius 0.1rem
    color #ccc
  .header-right
    width 1.24rem
    float right
    text-align center
    color #fff
    .arrow-icon
      font-size 0.24rem
      margin-left -0.04rem
</style>

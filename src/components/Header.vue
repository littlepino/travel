<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe624;</div>
    </div>
    <div class="header-input">
      <i class="iconfont">&#xe632;</i>
      输入城市景点游玩主题</div>
    <div class="header-right">城市
      <i class="iconfont arrow-icon">&#xe64a;</i>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~@/assets/styles/varibles.styl'
  .header
    display: flex
    line-height: .86rem
    background: #00bcd4
    color: #fff
    .header-left
      width: .64rem
      float: left
      .back-icon
        text-align: center
        font-size: .4rem
    .header-input
      flex: 1
      height: .64rem
      margin-top: .12rem
      line-height: .64rem
      margin-left: .2rem
      background: #fff
      border-radius: .1rem
      color: #ccc
      padding-left: .2rem;
    .header-right
      width: 1.24rem
      float: right
      text-align: center
      .arrow-icon
        font-size: .24rem
        margin-left: -.04rem

</style>

<template>
  <div>
    <div class="banner" @click='handleBannerClick'>
      <img class="banner-img" src="http://img1.qunarzz.com/sight/p0/1901/ea/ea459039354370daa3.img.jpg_600x330_fb7c3a59.jpg">
      <div class="banner-info">
        <div class="banner-title">世界公园(AAAA景区)</div>
        <div class="banner-number"><i class="iconfont banner-icon">&#xe692;</i>26</div>
      </div>
    </div>
    <common-gallary :imgs="imgs" v-show="showGallary" @close="handleGallaryClose"></common-gallary>
  </div>
</template>

<script>
import CommonGallary from '../../../common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  data () {
    return {
      showGallary: false,
      imgs: ['http://img1.qunarzz.com/sight/p0/1508/89/895a1b7add84f23faca053ce9e3153db.water.jpg_r_800x800_087730c7.jpg', 'http://img1.qunarzz.com/sight/p0/1906/e7/e7276de002459b50a3.img.jpg_r_800x800_5cdd4127.jpg']
    }
  },
  components: {
    CommonGallary
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false
    }
  }
}
</script>

<style lang="stylus" scoped>
  .banner
    position: relative
    overflow: hidden
    height: 0
    padding-bottom: 55%
    .banner-img
      width: 100%
    .banner-info
      position: absolute
      display: flex
      left: 0
      right: 0
      bottom: 0
      liner-height: .6rem
      color: #fff
      background-image: linear-gradient(to bottom, rgba(0,0,0,0),rgba(0,0,0,.8))
      .banner-title
        flex: 1
        font-size: .32rem
        padding: 0 .2rem
      .banner-number
        height: .32rem
        // margin-top: .14rem
        padding: 0 .4rem
        padding-bottom: .14rem
        line-height: .32rem
        border-radius: .2rem
        background: rgba(0, 0, 0, .8)
        font-size: .24rem
        .banner-icon
          font-size: .24rem
          padding-right: .1rem
</style>

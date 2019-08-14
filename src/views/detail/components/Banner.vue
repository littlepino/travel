<template>
  <div>
    <div class="banner" @click='handleBannerClick'>
      <img class="banner-img" :src="bannerImg">
      <div class="banner-info">
        <div class="banner-title">{{ this.sightName }}</div>
        <div class="banner-number"><i class="iconfont banner-icon">&#xe692;</i>{{ this.gallaryImgs.length }}</div>
      </div>
    </div>
    <fade-animation>
      <common-gallary :imgs="gallaryImgs" v-show="showGallary" @close="handleGallaryClose"></common-gallary>
    </fade-animation>
  </div>
</template>

<script>
import CommonGallary from '../../../common/gallary/Gallary'
import FadeAnimation from '../../../common/fade/Fade'
export default {
  name: 'DetailBanner',
  data () {
    return {
      showGallary: false
    }
  },
  components: {
    CommonGallary,
    FadeAnimation
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false
    }
  },
  props: {
    sightName: String,
    bannerImg: String,
    gallaryImgs: Array

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

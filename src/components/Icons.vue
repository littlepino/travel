<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div class="icon" v-for="item in page" :key="item.id">
          <div class="icon-img">
            <img class="icon-img-content" :src="item.url" alt="">
          </div>
          <p class="icon-desc">{{ item.desc }}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  data () {
    return {
      iconList: [
        {
          id: '001',
          url: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          desc: '景点门票'
        }, {
          id: '002',
          url: 'http://img1.qunarzz.com/piao/fusion/1803/3e/86314b2af03b7502.png',
          desc: '水上乐园'
        }, {
          id: '003',
          url: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20194/3ef092d0a89ffddb7f781cda30c8ae49.png',
          desc: '暑期大促'
        }, {
          id: '004',
          url: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          desc: '室内娱乐'
        }, {
          id: '005',
          url: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
          desc: '一日游'
        }, {
          id: '006',
          url: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20198/0f18f305d448365942f04b085d8f58bb.png',
          desc: '水上公园'
        }, {
          id: '007',
          url: 'http://img1.qunarzz.com/piao/fusion/1803/47/c2b659e048b11602.png',
          desc: '上海野生'
        }, {
          id: '008',
          url: 'http://img1.qunarzz.com/piao/fusion/1803/de/f26be47a6bf02a02.png',
          desc: '上海迪士尼'
        }, {
          id: '009',
          url: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          desc: '景点门票'
        }
      ]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8) // 当 index 小于8的时候，page 为 0，即 push 内的是第 0 页，当 index 大于 8 的时候，数据就会 push 到第一页，是，等于变成了一个大数组内两个数组，page 就是第数组内的数组
        if (!pages[page]) { 
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~@/assets/styles/varibles.styl'
  @import '~@/assets/styles/mixins.styl'
  .icons >>> .swiper-container
    height: 0
    padding-bottom: 50%
  .icon
      position: relative
      width: 25%
      height: 0
      float: left
      padding-bottom: 25%
      overflow: hidden
      .icon-img
        position: absolute
        top: 0
        left: 0
        right: 0
        bottom: .44rem
        box-sizing: border-box
        padding: 0.1rem
        img
          display: block
        .icon-img-content
          height: 100%
          margin: 0 auto
      .icon-desc
          position: absolute
          left: 0
          right: 0
          bottom: 0
          height: .44rem
          line-height: .44rem
          text-align: center
          color: $darkTextColor
          ellipsis()
</style>

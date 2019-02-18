<template>
    <div>
        <div class="banner" @click="handleBannerClick">
            <img class="banner-img" src="//img1.qunarzz.com/sight/p0/1812/18/18e166d74daa0d21a3.water.jpg_600x330_ca21c845.jpg" alt="">
            <div class="banner-info">
                <div class="banner-title">哈尔滨冰雪大世界</div>
                <div class="banner-number"><span class="iconfont banner-icon">&#xe692;</span> 8</div>
            </div>
        </div>
        <common-gallary :imgs="imgs" v-show="showGallary" @close="handleGallaryClose"></common-gallary>
    </div>
</template>
<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  data () {
    return {
      showGallary: false,
      imgs: ['http://img1.qunarzz.com/sight/p0/1812/18/18e166d74daa0d21a3.water.jpg_r_800x800_f17f44ef.jpg', 'http://img1.qunarzz.com/sight/p0/1812/b9/b93862426636deeca3.water.jpg_r_800x800_8c4ab2ab.jpg']
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false
    }
  },
  components: {
    CommonGallary
  }
}
</script>
<style lang="stylus" scoped>
.banner
  overflow hidden
  height 0
  padding-bottom: 55%
  position relative
  .banner-img
    width 100%
  .banner-info
    position absolute
    left 0
    right 0
    bottom 0
    line-height .6rem
    display flex
    color #fff
    background-image linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,0.8))
    .banner-title
      flex 1
      font-size 0.32rem
      padding 0 .2rem
    .banner-number
      padding 0 .4rem
      height .32rem
      line-height  .32rem
      border-radius .2rem
      background rgba(0,0,0,0.8)
      font-size .24rem
      margin-top .14rem
      .banner-icon
        font-size .24rem
</style>

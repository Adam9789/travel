<template>
    <div class="icons">
        <swiper :options="swiperOption">
            <swiper-slide v-for="(page,index) in pages" :key="index">
                <div class="icon" v-for="item in page" :key="item.id">
                    <div class="icon-img">
                        <img :src="item.imgUrl" alt="" class="icon-imgcontent">
                    </div>
                <p class="icon-desc">{{item.title}}</p>
                </div>
            </swiper-slide>
        <div class="swiper-pagination" slot="pagination"></div>
        </swiper>
    </div>
</template>
<script>
export default {
  name: 'Icons',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        autoplay: false
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      this.list.forEach((item, index) => {
        const page = Math.floor(index / 8)
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

.icons >>> .swiper-container
  height 0
  padding-bottom 58%
.icons
  margin-top .2rem
  .icon
    position relative
    width 25%
    padding-bottom 25%
    float left
    .icon-img
        position absolute
        top 0
        left 0
        right 0
        bottom .44rem
        box-sizing border-box
        padding .1rem
        .icon-imgcontent
          margin 0 auto
          display block
          height 100%
    .icon-desc
        position absolute
        bottom 0
        left 0
        right 0
        line-height .44rem
        height .44rem
        text-align center
        color #333
        overflow hidden
        text-overflow ellipsis
        white-space nowrap
</style>

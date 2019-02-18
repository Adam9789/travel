<template>
    <div class="container" @click="handleGallaryClick">
        <div class="wrapper">
            <swiper :options="swiperOption">
                <swiper-slide v-for="(item,index) in imgs" :key="index">
                    <img class="gallary-img" :src="item" alt="">
                </swiper-slide>
                <div class="swiper-pagination" slot="pagination"></div>
            </swiper>
        </div>
    </div>
</template>
<script>
export default {
  name: 'CommonGallary',
  props: {
    imgs: {
      type: Array,
      default () {
        return ['http://img1.qunarzz.com/sight/p0/1812/18/18e166d74daa0d21a3.water.jpg_r_800x800_f17f44ef.jpg', 'http://img1.qunarzz.com/sight/p0/1812/b9/b93862426636deeca3.water.jpg_r_800x800_8c4ab2ab.jpg']
      }
    }
  },
  methods: {
    handleGallaryClick () {
      this.$emit('close')
    }
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observeParents: true,
        observer: true
      }
    }
  }
}
</script>
<style lang="stylus" scoped>
.container >>> .swiper-container
  overflow inherit
.container
  position fixed
  left 0
  top 0
  right 0
  bottom 0
  z-index 4
  background #000
  display flex
  flex-direction column
  justify-content center
  .wrapper
    width 100%
    height 0
    padding-bottom 66.67%
    .gallary-img
      width 100%
    .swiper-pagination
      color #fff
      bottom -1rem
</style>

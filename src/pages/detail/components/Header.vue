<template>
    <div>
          <router-link tag="div" to="/" class="header-abs" v-show="showAbs">
            <div class="iconfont header-abs-back">&#xe624;</div>
          </router-link>
      <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">
          景点详情
        <router-link to="/">
            <div class="iconfont backicon">&#xe624;</div>
        </router-link>
      </div>
    </div>
</template>
<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      if (top > 60) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = {opacity}
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.header-abs
  position absolute
  left .2rem
  top .2rem
  width .8rem
  height .8rem
  border-radius .4rem
  background rgba(0,0,0,0.8)
  line-height .8rem
  text-align center
  .header-abs-back
    color #fff
    font-size .4rem
.header-fixed
  height .86rem
  line-height .86rem
  text-align center
  color #fff
  background $bgColor
  font-size .36rem
  position fixed
  top 0
  left 0
  right 0
  z-index 999
  .backicon
    width .64rem
    text-align center
    font-size .4rem
    position absolute
    top 0
    left 0
    color #fff
</style>

<template>
    <div class="list" ref="wrapper">
        <div>
            <div class="area">
                <div class="title border-topbottom">当前城市</div>
                <div class="button-list">
                    <div class="button-wrapper">
                        <div class="button">{{this.$store.state.city}}</div>
                    </div>
                </div>
            </div>
                    <div class="area">
                <div class="title border-topbottom">热门城市</div>
                <div class="button-list">
                    <div class="button-wrapper" v-for="item of hot" :key="item.id" @click="handleCityClick(item.name)">
                        <div class="button">{{item.name}}</div>
                    </div>
                </div>
            </div>
            <div class="area" v-for="(item ,key) in cities" :key="key" :ref="key">
                <div class="title border-topbottom">{{key}}</div>
                <div class="item-list">
                    <div class="item border-bottom" v-for="InnerItem in item" :key="InnerItem.id" @click="handleCityClick(InnerItem.name)">{{InnerItem.name}}</div>
                </div>
            </div>
       </div>
    </div>
</template>
<script>
import BScroll from 'better-scroll'
export default {
  name: 'CityList',
  props: {
    hot: Array,
    cities: Object,
    letter: String
  },
  methods: {
    handleCityClick (city) {
      this.$store.dispatch('changeCity', city)
      this.$router.push('/')
    }
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.wrapper)
  },
  // 用watch监听letter变化，一旦变了用BScoll提供的方法跳到某个元素
  watch: {
    letter () {
      if (this.letter) {
        const element = this.$refs[this.letter][0]
        this.scroll.scrollToElement(element)
      }
    }
  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.border-topbottom
  &:before
    border-color #cccccc
  &:after
    border-color #cccccc
.border-bottom
  &:before
    border-color #cccccc
.list
  position absolute
  overflow hidden
  top 1.58rem
  left 0
  right 0
  bottom 0
.title
  line-height  .5rem
  padding-left .2rem
  color #666
  background #eee
  font-size .26rem
.button-list
  padding .1rem .6rem .1rem .1rem
  overflow hidden
  .button-wrapper
    float left
    width 33.33%
    .button
      text-align center
      margin .1rem
      border .02rem solid #ccc
      padding .1rem 0
      border-radius .06rem
.item-list
  .item
    line-height  .74rem
    padding-left .2rem
</style>

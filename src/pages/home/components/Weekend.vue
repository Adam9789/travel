<template>
    <div>
        <div class="recommend-title">周末去哪</div>
        <ul>
            <li class="item border-bottom" v-for="item in list" :key="item.id">
                    <div class="item-img-wrapper">
                        <img class="item-img" :src="item.imgUrl" alt="">
                    </div>
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                </div>
            </li>
        </ul>
    </div>
</template>
<script>
export default {
  name: 'HomeWeekend',
  props: {
    list: Array
  }
}
</script>
<style lang="stylus" scoped>
.recommend-title
  line-height 1rem
  background #eee
  text-indent .2rem
.item-img-wrapper
  overflow hidden
  height 0
  padding-bottom 33.4%
.item-img
  width 100%
.item-info
  padding .1rem
  min-width 0
  .item-title
    line-height .54rem
    font-size .32rem
    overflow hidden
    white-space nowrap
    text-overflow ellipsis
  .item-desc
    line-height .4rem
    color #ccc
    overflow hidden
    white-space nowrap
    text-overflow ellipsis
</style>

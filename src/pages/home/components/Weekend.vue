<template>
    <div>
        <div class="recommend-title">周末去哪</div>
        <ul>
            <li class="item border-bottom" v-for="item in recommendList" :key="item.id">
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
  data () {
    return {
      recommendList: [
        {
          id: '0001',
          title: '哈尔滨温泉',
          desc: '这里是温泉旅行的好去处，设施最新，服务贴心，是最适合全家度假休闲的好去处',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1812/89/17a0bd303e45e0.jpg_r_640x214_8f7a2a88.jpg'
        },
        {
          id: '0002',
          title: '哈尔滨必游',
          desc: '冰雪之冠，富有异国情调的美丽都市',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/e3/e9761259adfc1d.jpg_r_640x214_21b96532.jpg'
        }
      ]
    }
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

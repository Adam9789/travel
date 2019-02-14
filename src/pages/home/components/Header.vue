<template>
  <div class="header">
    <div class="header-left">
        <div class="iconfont backicon">&#xe624;</div>
    </div>
    <div class="header-input">
        <span class="iconfont">&#xe632;</span>
        输入城市/景点/游玩主题
    </div>
    <div class="header-right">
        城市
        <span class="iconfont arrowicon">&#xe64a;</span>
    </div>
  </div>
</template>
<script>
export default {
  name: 'HomeHeader'
}
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl'
  .header
    line-height 0.86rem
    display flex
    background $bgColor
    color #fff
    .header-left
        width .64rem
        float left
        .backicon
            font-size .4rem
            text-align center
    .header-input
        flex 1
        border-radius .1rem
        background #ffffff
        margin-top .12rem
        margin-left .2rem
        padding-left .2rem
        height .62rem
        line-height .62rem
        color #ccc
    .header-right
        float right
        width 1.24rem
        text-align center
        .arrowicon
            font-size .24rem

</style>

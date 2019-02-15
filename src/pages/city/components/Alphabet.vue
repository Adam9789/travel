<template>
    <div class="header">
        <ul class="list" >
          <li class="item" v-for="(item,key) in cities" :key="key">{{key}}</li>
        </ul>
    </div>
</template>
<script>
export default {
  name: 'CityHeaderAlphabet',
  props: {
    cities: Object
  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.list
  position absolute
  right 0
  top 1.58rem
  bottom 0
  width .4rem
  text-align center
  display flex
  flex-direction column
  justify-content center
  .item
    line-height .4rem
    color $bgColor
</style>

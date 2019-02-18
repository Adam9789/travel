<template>
    <div>
        <detail-banner :sightName="sightName" :bannerImg="bannerImg" :gallaryImgs="gallaryImgs"></detail-banner>
        <detail-header></detail-header>
        <div class="content">
            <detail-list :list="list"></detail-list>
        </div>
    </div>
</template>
<script>
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
import axios from 'axios'
export default {
  name: 'Detail',
  components: {
    DetailBanner,
    DetailHeader,
    DetailList
  },
  data () {
    return {
      sightName: '',
      bannerImg: '',
      gallaryImgs: [],
      list: []
    }
  },
  methods: {
    getDetailInfo () {
      axios.get('/api/detail.json?id =' + this.$route.params.id)
        .then(this.handleGetDataSuccess)
    },
    handleGetDataSuccess (res) {
      res = res.data
      if (res.data && res.ret) {
        this.list = res.data.categoryList
        this.gallaryImgs = res.data.gallaryImgs
        this.bannerImg = res.data.bannerImg
        this.sightName = res.data.sightName
      }
    }
  },
  mounted () {
    this.getDetailInfo()
  }
}
</script>
<style lang="stylus" scoped>
.content
  height 30rem
</style>

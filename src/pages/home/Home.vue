<template>
  <div>
    <home-header :city="city"></home-header>
    <home-swiper :list="swiperList"></home-swiper>
    <home-icons :list="iconList"></home-icons>
    <home-recommend :list="recommendList"></home-recommend>
  </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeRecommend from './components/Recommend'
import HomeIcons from './components/Icons'
import axios from 'axios'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend
  },
  data () {
    return {
      city: '',
      swiperList: [],
      iconList: [],
      recommendList: []
    }
  },
  methods: {
    getHomeInfo () {
      axios.get('/api/index.json')
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        this.city = res.data.city
        this.swiperList = res.data.swiperList
        this.iconList = res.data.iconList
        this.recommendList = res.data.recommendList
      }
      console.log(res)
    }
  },
  mounted () {
    this.getHomeInfo()
  }
}
</script>

<style>

</style>

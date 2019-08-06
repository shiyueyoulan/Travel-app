<template>
  <div class = wrapper>
    <swiper :options="swiperOption">
      <swiper-slide v-for="item of swiperList" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl"/>
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [{
        id: '0001',
        imgUrl: 'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20198/ffb06b600df4c655d10a1dfef4a8d0e9.jpg_750x200_7b1aec5e.jpg'
      },
      {
        id: '0002',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1609/1b/371522f509580f02.jpg_750x200_8d978cde.jpg'
      },
      {
        id: '0003',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1610/f3/f39d9de1e92deb02.jpg_750x200_8cbc3f9b.jpg'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
.wrapper >>> .swiper-pagination-bullet-active
  background-color #fff
.wrapper
  height 0
  width 100%
  padding-bottom 26.25%
  .swiper-img
    width 100%
</style>

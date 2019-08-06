<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div class="icon"
              v-for="item of page"
              :key="item.id"
        >
          <div class="icon-img">
            <img class="icon-img-content" src='item.imgUrl'/>
            <p class="icon-desc">{{item.desc}}</p>
          </div>
        </div>
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'Icons',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination'
      },
      iconList: [{
        id: '0010',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
        desc: '景点门票'
      }, {
        id: '001',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
        desc: '景点门票'
      }, {
        id: '002',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/6a/45f595250c73d102.png',
        desc: '夏日玩水'
      }, {
        id: '003',
        imgUrl: 'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/a40ee278d67000f2a29d2e20f6a029b3.png',
        desc: '自然风光'
      }, {
        id: '004',
        imgUrl: 'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20194/730646c021800ebd1385872fe6212476.png',
        desc: '狮子峰'
      }, {
        id: '008',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
        desc: '景点门票'
      }, {
        id: '007',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/6a/45f595250c73d102.png',
        desc: '夏日玩水'
      }, {
        id: '006',
        imgUrl: 'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/a40ee278d67000f2a29d2e20f6a029b3.png',
        desc: '自然风光'
      }, {
        id: '005',
        imgUrl: 'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20194/730646c021800ebd1385872fe6212476.png',
        desc: '狮子峰'
      }]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
  .icons >>> .swiper-pagination-bullet-active
    background-color #fff
  .icons >>> .swiper-container
    height 0
    padding-bottom 50%
  .icon
    position relative
    float left
    width 25%
    height 0
    padding-bottom 25%
    overflow hidden
    .icon-img
      position absolute
      top 0
      left 0
      right 0
      bottom 0.44rem
      box-sizing border-box
      padding 0.1rem
      .icon-img-content
        display block
        margin 0 auto
        height 100%
    .icon-desc
      position absolute
      // bottom 0
      left 0
      right 0
      height 0.44rem
      line-height 0.44rem
      text-align center
      color #333
</style>

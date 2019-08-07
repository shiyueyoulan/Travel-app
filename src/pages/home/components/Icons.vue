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
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination'
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      this.list.forEach((item, index) => {
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
    margin-top 0.1rem
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

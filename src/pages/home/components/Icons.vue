<template>
  <div class="icons">
    <swiper>
      <swiper-slide  v-for="(page,index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-image">
            <img class="icon-image-content" :src="item.imgUrl ">
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>
<style lang="stylus" scoped>
  @import "~styles/varibles.styl"
  @import "~styles/mixins.styl"
    .icons >>> .swiper-container
      height 0
      padding-bottom 50%
    .icons
      margin-top .1rem
      .icon
        position relative
        float left
        width 25%
        height 0
        padding-bottom 25%
        overflow hidden
        .icon-image
          position absolute
          top: 0
          left 0
          right 0
          bottom .3rem
          box-sizing border-box
          padding .1rem
          .icon-image-content
            display block
            height 100%
            margin 0 auto
        .icon-desc
          position absolute
          bottom 0
          left 0
          right 0
          height .44rem
          line-height .44rem
          color $darkTestColor
          text-align center
          ellipsis()
</style>
<script>
export default{
  name: 'HomeIcons',
  props: {
    list: Array
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

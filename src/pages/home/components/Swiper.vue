<template>
  <div class="wrapper">
    <swiper :options="swiperOption" v-if="showSwiper">
      <!-- slides -->
      <swiper-slide v-for="item in list" :key="item.id">
        <img class="swiper-image" :src="item.imgUrl">
      </swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>
<style lang="stylus" scoped>
  .wrapper  >>>  .swiper-pagination-bullet-active
    background #fff
  .wrapper
    overflow hidden
    width 100%
    height 0
    padding-bottom 31.5%
    background #eee
    .swiper-image
      width 100%
</style>
<script>
export default{
  name: 'HomeSwiper',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true,
        autoplay: 1000
      }
    }
  },
  computed: {
    showSwiper () {
      return this.list.length
    }
  }
}

</script>

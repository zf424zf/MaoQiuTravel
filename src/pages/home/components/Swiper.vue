<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="item in swiperList" :key="item.id">
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
    padding-bottom 25.73%
    background #eee
    .swiper-image
      width 100%
</style>
<script>
export default{
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true,
        autoplay: 1000
      },
      swiperList: [
        {
          id: '001',
          imgUrl: 'https://img1.qunarzz.com/qs/1805/95/f650b837b5246302.jpg'
        }, {
          id: '002',
          imgUrl: 'https://img1.qunarzz.com/qs/1805/f6/ed3f589004da902.jpg'
        }
      ]
    }
  }
}

</script>

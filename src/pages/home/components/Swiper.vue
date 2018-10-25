<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
    <!-- slides -->
      <swiper-slide v-for="item of swiperList" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl" :alt="item.art">
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
        id: '001',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1810/eb/5cacf42b59e91e02.jpg_750x200_9c0a77b0.jpg',
        art: '图1'
      }, {
        id: '002',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1810/4a/5a96cf1ed2624002.jpg_750x200_89f31fc8.jpg',
        art: '图2'
      }]
    }
  }
}
</script>
<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background: #fff
  .wrapper
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 26.66%
    background: #eee
    .swiper-img
      width: 100%
</style>

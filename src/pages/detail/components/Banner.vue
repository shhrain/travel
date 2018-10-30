<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" :src="bannerImg" alt="万圣节">
      <div class="banner-info">
        <div class="banner-title">{{sightName}}</div>
        <div class="banner-number"><span class="iconfont banner-icon">&#xe692;</span>39</div>
      </div>
    </div>
    <fade-animation>
      <component-gallary :imgs="bannerImgs" v-show="showGallary" @close="handleGallaryClose"></component-gallary>
    </fade-animation>

  </div>
</template>
<script>
import ComponentGallary from 'components/gallary/Gallary'
import FadeAnimation from 'components/fade/FadeAnimation'
export default {
  name: 'DetailBanner',
  props: {
    sightName: String,
    bannerImg: String,
    bannerImgs: Array
  },
  data () {
    return {
      imgs: ['http://img1.qunarzz.com/sight/p0/1509/68/682dc0fa681a451d.water.jpg_r_800x800_06ee6464.jpg', 'http://img1.qunarzz.com/sight/p0/1601/12/124c976a879ad31a90.water.jpg_r_800x800_af1d4c9a.jpg'],
      showGallary: false
    }
  },
  components: {
    ComponentGallary,
    FadeAnimation
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false
    }
  }
}
</script>
<style lang="stylus" scoped>
  .banner
    position: relative
    overflow: hidden
    height: 0
    padding-bottom: 55%
    .banner-img
      width: 100%
    .banner-info
      display: flex
      position: absolute
      left: 0
      right: 0
      bottom: 0
      line-height: .6rem
      color: #fff
      background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8))
      .banner-title
        flex: 1
        font-size: .32rem
        padding:0 .2rem
        text-shadow: 0 1px 2px rgba(0,0,0,0.70);
      .banner-number
        height: .32rem
        line-height: .32rem
        margin-top: .14rem
        padding:0 .4rem
        border-radius: .2rem
        background: rgba(0, 0, 0, .8)
        font-size: .24rem
        .banner-icon
          font-size: .24rem
</style>

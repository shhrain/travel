<template>
  <div class="icons">
    <swiper>
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-img">
            <img class='icon-img-content' :src='item.imgUrl' :alt='item.desc'>
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
      <!-- <swiper-slide>
        <div class="icon">
          <div class="icon-img">
            <img class='icon-img-content' src='http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png' alt=''>
          </div>
          <p class="icon-desc">景点门票</p>
        </div>
      </swiper-slide> -->
    </swiper>
  </div>
</template>
<script>
export default {
  name: 'HomeIcons',
  data () {
    return {
      iconList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
        desc: '景点门票'
      }, {
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/12/216ce2e78b5f5f02.png',
        desc: '万圣狂欢'
      }, {
        id: '0003',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/8246f27355943202.png',
        desc: '游乐场'
      }, {
        id: '0004',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/50/26ffa31b56646402.png',
        desc: '海洋馆'
      }, {
        id: '0005',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
        desc: '动植物园'
      }, {
        id: '0006',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/47/c2b659e048b11602.png',
        desc: '溜娃儿'
      }, {
        id: '0007',
        imgUrl: 'https://img1.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png',
        desc: '打卡圣地'
      }, {
        id: '0008',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
        desc: '一日游'
      }, {
        id: '0009',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/b6/37560ece9c62b502.png',
        desc: '东部华侨城'
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
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
  .icons >>> .swiper-container
    height: 0
    padding-bottom: 50%
  .icon
    position: relative
    overflow: hidden
    float: left
    width: 25%
    height: 0
    padding-bottom: 25%
    .icon-img
      position: absolute
      top: 0
      left: 0
      right: 0
      bottom: .44rem
      box-sizing: border-box
      padding: .1rem
      .icon-img-content
        display: block
        margin: 0 auto
        height: 100%
    .icon-desc
      position: absolute
      left: 0
      right: 0
      bottom: 0
      height: .44rem
      line-height: .44rem
      color: $darkTextColor
      text-align: center
      ellipsis()
</style>

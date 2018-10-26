<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
          <img class="item-img" :src='item.imgUrl' :alt="item.title">
          <div class="item-info">
            <p class="item-title">{{item.title}}</p>
            <p class="item-desc">{{item.desc}}</p>
            <button class="item-button">查看详情</button>
          </div>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'HomeRecommend',
  data () {
    return {
      recommendList: [{
        id: '10001',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1810/4c/4c3e7f52ffd973b0a3.water.jpg_200x200_65b5a07f.jpg',
        title: '世界之窗',
        desc: '一个下午让你走遍全世界~'
      }, {
        id: '10002',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1810/22/226c137568f18ac0a3.water.jpg_200x200_81ac3ecf.jpg',
        title: '深圳欢乐谷',
        desc: '狂欢无罪，够胆你就来！~'
      }, {
        id: '10003',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1810/4c/4c3e7f52ffd973b0a3.water.jpg_200x200_65b5a07f.jpg',
        title: '世界之窗',
        desc: '一个下午让你走遍全世界~'
      }, {
        id: '10004',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1810/4c/4c3e7f52ffd973b0a3.water.jpg_200x200_65b5a07f.jpg',
        title: '世界之窗',
        desc: '一个下午让你走遍全世界~'
      }, {
        id: '10005',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1810/4c/4c3e7f52ffd973b0a3.water.jpg_200x200_65b5a07f.jpg',
        title: '世界之窗',
        desc: '一个下午让你走遍全世界~'
      }]
    }
  }
}
</script>
<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
  .title
    margin-top: .2rem
    line-height .8rem
    background #eee
    text-indent: .2rem
    ellipsis()
  .item
    overflow: hidden
    display: flex
    height: 1.9rem
    .item-img
      width: 1.7rem
      height: 1.7rem
      padding: .1rem
    .item-info
      flex: 1
      padding: .1rem
      min-width: 0
      .item-title
        line-height: .54rem
        font-size: .32rem;
        ellipsis()
      .item-desc
        line-height: .4rem
        color: #ccc
        ellipsis()
      .item-button
        line-height: .44rem
        margin-top: .16rem
        background: $bgColor
        padding: 0 .2rem
        border-radius: .06rem
        color: #fff
        text-align: center
</style>

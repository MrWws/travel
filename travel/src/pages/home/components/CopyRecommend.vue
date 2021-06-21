<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item  border-bottom">
        <img class="item-img" src="https://imgs.qunarzz.com/sight/p0/201404/23/04b92c99462687fa1ba45c1b5ba4ad77.jpg_200x200_4ab5da75.jpg" />
        <div class="item-info">
          <p class="item-title">大连圣亚海洋世界</p>
          <p class="item-desc">浪漫大连首站，浪漫的海洋主题乐园</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend'
}
</script>

<style lang="stylus" scoped>
  .title
    margin-top .2rem
    line-height .8rem
    background #eee
    text-indent .2rem
  .item
    display felx
    height 1.9rem
    overflow hidden
    .item-img
      width 1.7rem
      height 1.7rem
      padding .1rem
    .item-info
      flex 1
      padding .1rem
      .item-title
        line-height .54rem
        font-size .32rem
      .item-desc
        line-height .4rem
        color #ccc
</style>

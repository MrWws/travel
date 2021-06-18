<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="item  border-bottom" v-for="item of recommendList" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl"/>
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  data() {
    return {
      recommendList: [{
      id: '0001',
      imgUrl: 'https://imgs.qunarzz.com/sight/source/1812/b4/e9d7f043c4fadf.jpg_r_640x214_713df0cf.jpg',
      title: '大连圣亚海洋世界',
      desc: '浪漫大连首站，浪漫的海洋主题乐园'
    },{
      id: '0002',
      imgUrl: 'https://imgs.qunarzz.com/sight/source/1812/b4/e9d7f043c4fadf.jpg_r_640x214_713df0cf.jpg',
      title: '大连圣亚海洋世界',
      desc: '浪漫大连首站，浪漫的海洋主题乐园'
    },{
      id: '0003',
      imgUrl: 'https://imgs.qunarzz.com/sight/source/1812/b4/e9d7f043c4fadf.jpg_r_640x214_713df0cf.jpg',
      title: '大连圣亚海洋世界',
      desc: '浪漫大连首站，浪漫的海洋主题乐园'
    }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .title
    margin-top .2rem
    line-height .8rem
    background #eee
    text-indent .2rem
  .item-img-wrapper
    width 100%
    overflow hidden
    height 0
    padding-bottom 33.9%
    .item-img
      width 100%
  .item-info
    flex 1
    padding .1rem
    min-width 0
    .item-title
      line-height .54rem
      font-size .32rem
      ellipsis()
    .item-desc
      line-height .4rem
      color #ccc
      ellipsis()
</style>

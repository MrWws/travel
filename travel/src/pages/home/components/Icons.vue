<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page, index) in pages" :key="index">
        <div class="icon" v-for="item in page" :key="item.id">
          <div class="icon-img">
            <img class="icon-img-content" :src="item.imgUrl" />
          </div>
          <p class="icon-desc">{{ item.desc }}</p>
        </div>
      </swiper-slide>
      <!-- 用于分页 提升用户体验 -->
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  props:{
    list: Array
  },
  data() {
    return {
      swiperOption: {
        pagination: '.swiper-pagination'
      }
    }
  },
  // 计算属性里的算法就是帮助我们把一维的九条数组拆分成二维数组
  // 然后页码和对应的数据项做一个关联
  computed: {
    pages() {
      const pages = []
      // forEach() 方法用于调用数组的每个元素，并将元素传递给回调函数。
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
// ~默认代表当前项目的根目录
//styles为别名
// alias: {
//       'vue$': 'vue/dist/vue.esm.js',
//       '@': resolve('src'),
//       'styles': resolve('src/assets/styles'),
//     }
@import '~styles/varibles.styl';
@import '~styles/mixins.styl';
  .icons >>> .swiper-container
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 50%
  .icons
    margin-top .1rem
    .icon
      height: 0
      position: relative
      overflow: hidden
      width: 25%
      padding-bottom: 25%
      float: left
      .icon-img
        position: absolute
        top: 0
        left: 0
        right 0
        bottom .44rem
        .icon-img-content
          height 100%
          display block
          margin 0 auto
      .icon-desc
        position absolute
        left: 0
        right 0
        bottom 0
        height .44rem
        line-height .44rem
        text-align center
        color $darkTextColor
        ellipsis()
</style>


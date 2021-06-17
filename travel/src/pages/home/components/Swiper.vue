<template>
  <!-- 在swiper外面加上一层div，是为了防止在网速慢的情况下抖动的bug，用户体验不好 -->
  <div class="warpper">
    <swiper :options="swiperOption">
      <swiper-slide v-for="item in swiperList" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl" />
      </swiper-slide>
      <!-- 用于分页 -->
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  // ES6 data后面要有空格
  data () {
    return {
      swiperOption: {
        // 参数选项,显示小点
        pagination: '.swiper-pagination',
        // 循环轮播
        loop: true,
        // 每张播放时长1秒，自动播放
        autoplay: 1000,
        // 滑动速度
        speed: 500
      },
      swiperList: [
        {
          id: '0001',
          imgUrl:
            'http://img1.qunarzz.com/piao/fusion/1802/e3/62ce7362ca051d02.jpg_640x200_6db551b7.jpg'
        },
        {
          id: '0002',
          imgUrl:
            'http://img1.qunarzz.com/piao/fusion/1801/93/ce59d182aca07102.jpg_640x200_ba03d44c.jpg'
        }
      ]
    }
  }
}
</script>

<style lang="stylus" scoped>
// 样式进行了穿透  只要warpper下出现swiper-pagination-bullet-active类名就变色
// 这样就不受scoped作用域的限制
.warpper >>> .swiper-pagination-bullet-active {
  background-color: #fff !important;
}
.warpper {
  overflow: hidden;
  width: 100%;
  height: 0;
  padding-bottom: 31.25%;
  background: #eee;

  .swiper-img {
    width: 100%;
  }
}
</style>


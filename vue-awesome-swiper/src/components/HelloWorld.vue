<template>
  <div class="mySwiper">
    <swiper :options="swiperOption"
            ref="mySwiper"
            class="swiper-cont">
      <swiper-slide v-for="(item,index) in picList"
                    :key="index"
                    class="fullImg">
        <div>
          <span class="showBig">查看大图</span>
          <div>{{ item }}</div>
          <span class="bottomTime">{{index}}</span>
        </div>
      </swiper-slide>
      <!-- <div class="swiper-button-prev"
                       slot="button-prev"
                       @click.stop="prev()"
                       v-show="swiperBtn"></div>
                  <div class="swiper-button-next"
                       slot="button-next"
                       @click.stop="next()"
                       v-show="swiperBtn"></div> -->
    </swiper>
    <div class="prev"
         @click="prev"
         v-show="swiperBtn && picList.length > 0">
    </div>
    <div class="next"
         @click="next"
         v-show="swiperBtn && picList.length > 0">
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      picList: [1, 2, 3, 4],
      swiperBtn: false, // 默认隐藏
      swiperOption: {
        // initialSlide: 4, // 设定初始化时slide的索引
        spaceBetween: 30, // 在silde之间的距离
        slidesPerView: 1,
        keyboard: false,
        pagination: {
          el: '.swiper-pagination',
          clickable: true
        },
        navigation: {
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev',
          hideOnClick: false,
          disabledClass: 'my-button-disabled',
          hiddenClass: 'my-button-hidden'
        },
        on: {
          // 使用es6的箭头函数，使this指向vue对象
          click: () => {
            // 通过$refs获取对应的swiper对象
            // let swiper = this.$refs.mySwiper.swiper;
            // let i = swiper.realIndex;
          }
          // keyPress: function (event) {
          //   let i = this.swiper.realIndex;
          //   if (event === 37) {
          //     // this.prev();
          //     // this.getImg(-1);
          //     this.exitTime = this.picList[i].uploadTime;
          //   } else if (event === 39) {
          //     // this.getImg(1);
          //     this.exitTime = this.picList[i].uploadTime;
          //     // this.next();
          //   }
          // }.bind(this)
        }
      }
    }
  },
  methods: {
    prev () {
    },
    next () {

    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="stylus" rel="stylesheet/stylus">
.mySwiper
  .swiper-cont
    width 400px
    height 200px
    .swiper-wrapper
      .fullImg
        width 400px
        height 200px
        background-color #cccccc
</style>

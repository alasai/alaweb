<template>
  <view v-if="async">
    <swiperItem1 v-if="swiperModel.swiperType == 1" :swiperModel="swiperModel"></swiperItem1>
    <swiperItem2 v-if="swiperModel.swiperType == 2" :swiperModel="swiperModel"></swiperItem2>
    <swiperItem3 v-if="swiperModel.swiperType == 3" :swiperModel="swiperModel"></swiperItem3>
    <swiperItem4 v-if="swiperModel.swiperType == 4" :widget="widget" :swiperModel="swiperModel"></swiperItem4>
    <swiperItem5 v-if="swiperModel.swiperType == 5" :swiperModel="swiperModel.swiperList"></swiperItem5>
  </view>
</template>

<script>
  import swiperItem1 from './styles/swiper-item-1'
  import swiperItem2 from './styles/swiper-item-2'
  import swiperItem3 from './styles/swiper-item-3'
  import swiperItem4 from './styles/swiper-item-4'
  import swiperItem5 from './styles/swiper-item-5'
  export default {
    props: {
      widget: {}
    },
    components: {
      swiperItem1,
      swiperItem2,
      swiperItem3,
      swiperItem4,
      swiperItem5
    },
    data () {
      return {
        swiperModel: null,
        async: false
      }
    },
    mounted () {
      this.init()
    },
    methods: {
      init () {
        if (this.widget && this.widget.value) {
          this.swiperModel = this.widget.value.swiperForm
        }
        this.async = true
      }
    }
  }
</script>

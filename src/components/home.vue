<template>
  <swiper :pagination="true" class="mySwiper mb-5">
    <swiper-slide><img src="images/banner01.jpg" alt=""></swiper-slide>
    <swiper-slide><img src="images/banner02.jpg" alt=""></swiper-slide>
    <swiper-slide><img src="images/banner03.jpg" alt=""></swiper-slide>
    <swiper-slide><img src="images/banner04.jpg" alt=""></swiper-slide>
    <swiper-slide><img src="images/banner05.jpg" alt=""></swiper-slide>
  </swiper>
  <div class="best">
    <div class="container mb-5">
      <h2>BEST상품</h2>
      <p>MUSINSA BEST상품을 소개합니다.</p>
      <div class="row">
        <div class="col-sm-6 col-md-3" v-for="(item,i) in 4" :key="i">
          <img :src="pdata[i].image" alt="" class="w-100">
          <p>{{pdata[i].title}}</p>
          <p>{{pdata[i].price.toLocaleString()}}원</p>
          <p>{{pdata[i].content}}</p>
        </div>
      </div>
      <div class="btn btn-primary d-block m-auto" style="width:100px">
        <router-link to="/product">MORE</router-link>
      </div>
    </div>
  </div>
</template>

<script>

// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from 'swiper/vue';

import "swiper/components/pagination/pagination.min.css"

// Import Swiper styles
import 'swiper/swiper.scss';

// import Swiper core and required modules
import SwiperCore, {
  Pagination
} from 'swiper/core';

// install Swiper modules
SwiperCore.use([Pagination]);
export default {
  props:['pdata'],
  components: {
    Swiper,
    SwiperSlide,
  },
}
</script>

<style>
.best h2 {text-align: center;}
.best h2:after {
  content:''; width: 30px; height: 1px; background: #333; display: block;
  margin: 20px auto;
  }
.best p {text-align: center;}
</style>
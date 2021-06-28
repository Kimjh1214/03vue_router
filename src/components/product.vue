<template>
  <div class="product">
    <div class="container mb-5 px-0">
        <h2>상품</h2>
        <p>MUSINSA 상품을 소개합니다.</p>
        <div class="row">
          <div class="col-sm-6 col-md-3" v-for="(item,i) in pdata" :key="i">
            <img :src="pdata[i].image" alt="" class="w-100">
            <div @click="$emit('pOpen',pdata[i].id)">
              <p>{{pdata[i].title}}</p>
              <p><b>{{pdata[i].price.toLocaleString()}}원</b></p>
            </div>
          </div>
        </div>
      </div>
  </div>
</template>

<script>
export default {
  name:'product',
  props:['pdata']
}
</script>

<style>
.product h2 {text-align: center;}
.product h2:after {
  content:''; width: 30px; height: 1px; background: #333; display: block;
  margin: 20px auto;
  }
.product p {text-align: center;}
</style>
<template>

  <top-header/>
  <router-view 
  :pdata="pdata" 
  @pOpen="pView=true; pNum=$event"
  :bdata="bdata"
  @bOpen="bView=true; bNum=$event"
  >
  </router-view> 
  <bottom-footer></bottom-footer>
  
  <transition name="show" style="position:relative; z-index:100;"> 
    <p-pop
    :pdata="pdata"
    :pView="pView"
    :pNum="pNum"
    @pClose="pView=false"
    >
    </p-pop>
  </transition>
  <b-pop
  :bdata="bdata"
  :bView="bView"
  :bNum="bNum"
  @bClose="bView=false"
  >
  </b-pop>
</template>

<script>
import header from './components/header.vue'
import footer from './components/footer.vue'
import pdata from './pdata.js'
import pPop from './components/pPop.vue'
import bdata from './bdata.js'
import bPop from './components/bPop.vue'

export default {
  name:'app',
  components:{
    'top-header':header,
    'bottom-footer':footer,
    'p-pop':pPop,
    'b-pop':bPop,
  },
  data(){
    return{
      bdata:bdata,
      pdata:pdata,
      pView:false,
      pNum:0,
      bView:false,
      bNum:0,
    }
  }
}
</script>

<style>
  .pPop{
    position: fixed;  background: #fff; width: 80%; top: 50%; left: 50%;
    transform:translate(-50%, -50%); box-shadow:0 0 10px rgba(0,0,0,.5);
    border-radius: 10px; padding: 20px;
  }
  .bPop{
    position: fixed;  background: #fff; width: 80%; top: 50%; left: 50%;
    transform:translate(-50%, -50%); box-shadow:0 0 10px rgba(0,0,0,.5);
    border-radius: 10px; padding: 20px;
  }
  @media screen and (min-width:900px) {
    .pPop {width: 550px;}
  }

  .show-enter-from,.show-leave-to{opacity:0; }
  .show-enter-active,.show-leave-active{transition:0.5s}
  .show-enter-to,.show-leave-from{opacity:1;}
</style>
<template>

  <p-pop 
  :pdata="pdata" 
  :pView="pView" 
  :pNum="pNum"
  @pClose="pView=false"
  >
  </p-pop>
  <top-header/>
  <router-view 
  :pdata="pdata" 
  @pOpen="pView=true; pNum=$event"
  >
  </router-view> 
  <bottom-footer></bottom-footer>
  
</template>

<script>
import header from './components/header.vue'
import footer from './components/footer.vue'
import pdata from './pdata.js'
import pPop from './components/pPop.vue'

export default {
  name:'app',
  components:{
    'top-header':header,
    'bottom-footer':footer,
    'p-pop':pPop,
  },
  data(){
    return{
      pdata:pdata,
      pView:false,
      pNum:0,
    }
  }
}
</script>

<style>
  .pPop{
    position: fixed; z-index:10; background: #fff; width: 80%; top: 50%; left: 50%;
    transform:translate(-50%, -50%); box-shadow:0 0 10px rgba(0,0,0,.5);
    border-radius: 10px; padding: 20px;
  }
  @media screen and (min-width:900px) {
    .pPop {width: 550px;}
  }
</style>
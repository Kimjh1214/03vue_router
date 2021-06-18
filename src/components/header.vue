<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <a class="navbar-brand" href="#">MUSINSA</a>
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNav">
      <ul class="navbar-nav ml-auto">
        <li class="nav-item active" v-for="(item,i) in menu" :key="i" @click="close">
          <router-link class="nav-link" :to="menu[i].link">{{menu[i].title}}</router-link>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  name:'header',
  data(){
    return{
      menu:[
        {title:'home',link:'/'},
        {title:'product',link:'/product'},
        {title:'board',link:'/board'},
      ]
    }
  },
  methods:{
    close:function(){
      document.getElementById("navbarNav").classList.remove("show");
    }
    // ()=>{} == function(){}
  }

}
</script>

<style>

</style>
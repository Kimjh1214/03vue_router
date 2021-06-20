<template>
  <div v-if="bView==true">
      <div class="bPop text-center">
        <h4>{{bdata[bNum].title}}</h4>
        <p>{{bdata[bNum].content}}</p>
        <button class="btn btn-primary" @click="$emit('bClose')">닫기</button>
      </div>
    </div>
</template>

<script>
export default {
 name:'bPop',
 props:['bdata','bView','bNum']
}
</script>

<style>

</style>
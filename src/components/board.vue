<template>
  <div class="board">
    <div class="container mb-5 px-0">
      <h2>board</h2>
      <p>게시판 입니다.</p>
      <table class="table">
        <thead class="thead-dark">
          <tr>
            <th scope="col">순서</th>
            <th scope="col">제목</th>
            <th scope="col">날짜</th>
          </tr>
        </thead>
        <tbody>
            <tr v-for="(item,i) in bdata" :key="i">
              <th scope="row">{{bdata[i].idx+1}}</th>
              <td @click="$emit('bOpen',bdata[i].idx)">{{bdata[i].title}}</td>
              <td>{{bdata[i].date}}</td>
            </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  name:'board',
  props:['bdata']
}
</script>

<style>
.board h2 {text-align: center;}
.board h2:after {
  content:''; width: 30px; height: 1px; background: #333; display: block;
  margin: 20px auto;
  }
.board p {text-align: center;}
</style>
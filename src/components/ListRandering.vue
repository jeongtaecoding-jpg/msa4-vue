<script setup>
import axios from 'axios';
import { ref } from 'vue';

 const arr = [3, 4, 2, 5];
 
 const data = ref([]);
 
async function getPicsum() {
  try {
    const url = 'https://picsum.photos/v2/list?page=40&limit=3';
    const res = await axios.get(url);
    data.value.push(...res.data);
    // ...(스프레드 오퍼레이터) : 배열 앞에 '...'을 붙여 각 요소에 ,(콤마)를 구분자로 분해나는 문법
  } catch(error) {
    console.log(error);
  }
}
getPicsum();

</script>

<template>
  <h1>리스트 렌더링</h1>

  <div class="container">
    <div class="card" v-for="item in data" :key="item.id">
      <div class="card-img" :style="{backgroundImage: `url('${item.download_url}')`}"></div>
     <span>{{ item.author }}</span>
    </div>
  </div>

  <!-- val이랑 key는 꼭 같이 적자! -->
  <div v-for="(val, key) in arr" :key="key">
    <p>{{ val }}</p>
  </div>

  <div v-for="val in 5">
    <p>{{val}} 회</p>
  </div>
</template>

<style>
.container {
  padding: 20px;
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 10px;
}

.card {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  gap: 10px;
}

.card-img {
  padding-top: 60%;
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
}
</style>

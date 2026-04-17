<script setup>
import { ref } from 'vue';

const flg = ref(true);
const num = ref(0);
setInterval(() => {
  num.value++;
}, 200);
</script>

<template>
  <!-- 조건부 렌더링 -->
  <button type="button" @click="flg = !flg">온/오프</button>
  <h1 v-show="flg">브이 쇼</h1>
  <h1 v-if="num % 3 === 0" style="color: red;">빨강</h1>
  <h1 v-else-if="num % 2 === 0" style="color: blue;">파랑</h1>
  <h1 v-else-if="num % 5 === 0" style="color: yellow;">노랑</h1>
  <h1 v-else>없음</h1>
</template>

<style>

</style>

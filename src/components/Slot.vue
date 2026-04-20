<script setup>
// 템플릿 컨텐츠를 부모 컴포넌트에서 자식 컴포넌트로 전달하고, 자식 컴포넌트에서 렌더링
// - 자식 컴포넌트에서는 출력하고 싶은 위치에 <slot> 태그를 작성
import { ref } from 'vue';
import SlotChild from './SlotChild.vue';

const cnt = ref(0);
</script>

<template>
  <h1>슬롯</h1>
  <button type="button"></button>
  <SlotChild>
    <h2>보내줄 슬롯: {{ cnt }}</h2>
    <h3>아아아 {{ cnt2 }}</h3>
  </SlotChild>
</template>

<style>

</style>

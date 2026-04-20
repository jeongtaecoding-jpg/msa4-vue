<script setup>
// 자식 컴포넌트에서는 defineProps()를 이용해 넘어온 데이터 선언
// - 이때 부모 컴포넌트에서 넘겨줄 때 사용한 키를 사용해 선언
// - 데이터 타입도 지정

// 이렇게도 가능 -> const props = defineProps({
//   'cnt': Number,
//   'page': Number,
// });
defineProps(['cnt', 'page']);  


// 자식 컴포넌트에서는 defineEmits()를 이용해 넘어온 컴포넌트 이벤트 선언
// - 이때 부모 컴포넌트에서 넘겨줄 때 사용한 이벤트 명을 사용해 선언
defineEmits(['minusCnt']);
// const emit = defineEmits(['minusCnt']);  
// (단!! 이 경우엔 아래 클릭 절의 emit 앞의 '$'가 빠져야 함)
</script>

<template>
  <h1>{{page}}프롭스 자식 컴포넌트 : {{ cnt }}</h1>
  <button type="button" @click="$emit('minusCnt', 10)">감소(자식쪽)</button>
  <!-- props.cnt가 아닌 cnt만 쳐도 적용이 됨(page도 마찬가지)  -->
</template>

<style scoped>

</style>

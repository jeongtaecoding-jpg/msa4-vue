<script setup>
  // js 코드 작성 부분
  import ConditionalRendering from './components/ConditionalRendering.vue';
  import DataBinding from './components/DataBinding.vue';
  import EventHandling from './components/EventHandling.vue';
  import ListRandering from './components/ListRandering.vue';
  import Watchers from './components/Watchers.vue';
  import Props from './components/Props.vue';
  import Slot from './components/Slot.vue';
  import MyTransition from './components/MyTransition.vue';
  
  import LifeCycle from './components/LifeCycle.vue';
  import { ref } from 'vue';

  const flgLifeCycle = ref(true);
</script>

<template>
  <!-- HTML 작성 부분 -->
  <DataBinding v-if="false"/>
  <EventHandling v-if="false"/>
  <ConditionalRendering v-if="false"/>
  <ListRandering v-if="false"/>
  <Watchers v-if="false"/>
  <Props v-if="false"/>
  <Slot v-if="false"/>
  <!-- Slot 등은 문제없이 동작함(인식 문제임) 다만, 예약어 등은 안 쓰는 게 좋음 -->
   <MyTransition v-if="false"/>
   <LifeCycle v-if="flgLifeCycle"/>
   <button type="button" @click="flgLifeCycle = !flgLifeCycle">라이프사이클 컴포넌트 토글</button>
</template>

<style>
/* CSS 작성부분 */
</style>

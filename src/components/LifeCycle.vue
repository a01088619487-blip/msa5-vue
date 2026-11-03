<script setup>
import { onBeforeMount, onMounted } from "vue";

// 마운트단계 :돔을 생성하는 단계  [딱 한번만 실행이된다.]
onBeforeMount(() => {
  alert("마운트 전에 실행됩니다.");
}); //함수
onMounted(() => {
  alert("마운트 후에 실행됩니다.");
});
//팍업창인건가?=ㅅ=;;
</script>

<template>
  <h2>Life Cycle</h2>
</template>

<style scoped></style>

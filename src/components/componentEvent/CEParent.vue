<script setup>
import CEChild from "./CEChild.vue";
import { ref } from "vue";

const count = ref(0);

// 카운트를 올리는 함수를 부모쪽에 먼저 적어둔다.
const addCount = () => {
  count.value++;
};
//내가 넣은 벨류에 곱하기!  파라미터 만들어야함.
const multiCount = (val) => {
  count.value *= val;
};
</script>

<template>
  <h2>CE Parent</h2>
  <p>카운트 : {{ count }}</p>
  <CEChild @addCount="addCount" @multiCount="multiCount" />
</template>

<style scoped></style>

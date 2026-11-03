<script setup>
import { ref } from "vue";
import Child from "./Child.vue";
const user = ref({
  id: 1,
  username: "홍길동",
  age: 20,
});
const str = ref("전달 문자열");
// const str = ''; 도가능
</script>

<template>
  <h2>Parent</h2>
  <Child :item="user" :str="str" />
  <!-- <Child :내가 지어주는이름="user" /> 
   (이름은 내맘대로해도되는데 예약어랑 안겹치게!)-->
</template>

<style scoped></style>
<!-- scoped 내가 지정한곳에만 영향이 가게 해준다
 스타일 전파라고 부른다 -->

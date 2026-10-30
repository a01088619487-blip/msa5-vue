<script setup>
// 뷰 현재  3버전 예전엔 2v 이엿듬
// 컴포지션 '반드시' setup 옵션을 줘야 사용가능하다
import { ref } from "vue";

const count = ref(0);
</script>

<!--template는 HTML과 가장 비슷한데 '특수'속성명이 있다-->
<!--ex) 특수 속성명 ☞ 동적으로 바꾸고싶을때 
<img src=""> 이걸   <img : src=""> 이런식으로 넣어야함 -->
<template>
  <!-- 버튼 이있고 누를때 1개씩 올라가게 만들기 -->
  <div @click="count++" class="btn-cnt">count is {{ count }}</div>
  <!-- ref로 인해서 카운트값을 0으로 햇기에 화면에 0이 출력된다. -->
  <!-- click함수에 콜백함수 넣으면됨 -->
  <button @click="count = 0">Count Reset</button>
</template>

<style>
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
#app {
  display: flex;
  flex-direction: row;
  gap: 15px;
  padding: 20px;
}
button {
  width: 100px;
  height: 100px;
  background-color: darkseagreen;
}
.btn-cnt {
  width: 100px;
  height: 100px;
  background-color: rgb(224, 255, 166);
}
</style>

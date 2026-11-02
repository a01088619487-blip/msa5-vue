<!-- 조건부 랜더링 -->
<script setup>
import { ref } from "vue";
const num = ref(0);
const flg = ref(true);
</script>

<template>
  <h1>APP Component</h1>
  <!-- 조건부 랜더링은 템플릿에 적어야함. -->
  <input type="number" v-model="num" />
  <p v-if="num === 0">0입니다.</p>
  <p v-else-if="num % 2 === 0">짝수 입니다.</p>
  <p v-else>홀수 입니다.</p>
  <hr />
  <button :class="{ 'btn-toggle': flg === false }" @click="flg = !flg">
    토글
  </button>
  <!-- flg = !flg 플래그에 대입연산자를 한다 !기존의값을 반전시키는것
   대입연사자는 오른쪽 코드가 먼저 실행된다.그래서 현재 트루가 펄스로 바뀌고 
   플래그가 펄스로 바껴서 대입연사자 결과는 펄스로 바뀐상태임. 근데 
   뜬금없는데 토글의 기능이 뭐임 'ㅅ';; -->
  <p v-if="flg">v-if</p>
  <p v-show="flg">v-show</p>
  <!-- 이렇게하면 외부적으론 역할을 같지만 내부상으로는 다르다
   off를 하면  v-if는 코드가 없고 v-show는 잇음  -->
</template>

<style>
.btn-toggle {
  background-color: rgb(249, 250, 181);
}
</style>

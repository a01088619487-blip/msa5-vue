<script setup>
// 뷰 현재  3버전 예전엔 2v 이엿듬
// 컴포지션 '반드시' setup 옵션을 줘야 사용가능하다
import { ref } from "vue";

const count = ref(0);
const bgColor = ref("");
// bgColor 안에 ref 객체가 들어가있음.\
const email = ref("aaaa");
// 양반향데이터바인딩.
const toggleBgColor = () => {
  if (bgColor.value === "") {
    // ref객체를 가져올려면 .value라는 걸 불러야함.
    bgColor.value = "bg-red";
  } else {
    bgColor.value = "";
  }
}; // 빈문자열인지 아닌지 확인하고 빈문자열에 레드라는걸 넣는?
//접근하는 영역ㅇㅔ 차이가 잇다.
</script>

<!--template는 HTML과 가장 비슷한데 '특수'속성명이 있다-->
<!--ex) 특수 속성명 ☞ 동적으로 바꾸고싶을때 
<img src=""> 이걸   <img : src=""> 이런식으로 넣어야함 -->
<template>
  <h1>APP Component</h1>
  <!-- 버튼 이있고 누를때 1개씩 올라가게 만들기 -->
  <div @click="count++" class="btn-cnt" :class="bgColor">
    count is {{ count }}
  </div>
  <!-- ref로 인해서 카운트값을 0으로 햇기에 화면에 0이 출력된다. -->
  <!-- click함수에 콜백함수 넣으면됨 -->
  <!-- : class 디렉티브 속성 이라고 부른다.
    콜론울 붙으면...반응성있게 조작할수있는-->
  <button @click="count = 0" class="btn-reset">Count Reset</button>
  <button @click="count--">Cound Down</button>
  <button @click="bgColor = 'bg-red'">Rde</button>
  <!-- vue는"''"텍스트 스트링이다.. 엔진네에서 특수기호를 인식해서 
   어디서부터 어디까지가 무슨속성인지 알수있게.. 오인식을 없애기 위해!
   여기서는 ''이것도 문자열로 인식할수있게 도와준다.? 
   엥 그래서 벡티도 같이 써도 인식이 되네 ㅇ0ㅇ  -->
  <button @click="bgColor = ''">cadetblue</button>
  <!-- 템플린에서는 value없이 적급이 가능하다 -->
  <button @click="toggleBgColor()">Toggle</button>
  <!-- 여기 토글로인하여 독특한문자가잇음 
    ()넣어도 실행이 가능함  뷰가 자동으로 설정해주는거임 
    [바닐라에이엔스.?에서는 자바스크립에()넣으면 안됨,파라미터에선 ()붙여야한다'ㅅ' ] -->
  <br /><br />
  <!-- 양반향데이터바인딩 -->
  <input type="text" class="email" id="email" v-model="email" />
  <!-- :value="email" 쓰는게 아니라 v-model="email"인 양반향데이터를 사용한다-->
  {{ email }}
  <!-- {{ email }} 출력값 -->
  <!-- 이벤트를 사용할때 @를 사용하면된다! 이벤트 -클릭, 스크롤,키,마우스 설정 -->

  <!-- Components 분리 하는법 [간단하게] -->
</template>

<style>
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
#app {
  /* display: flex;
  flex-direction: row; */
  gap: 15px;
  padding: 20px;
}
button {
  width: 100px;
  height: 100px;
  background-color: darkseagreen;
}
.btn-cnt {
  width: 200px;
  height: 100px;
  background-color: rgb(224, 255, 166);
}
.btn-reset {
  width: 100px;
  height: 100px;
  background-color: cadetblue;
}
.bg-red {
  background-color: #ff0000;
}
</style>

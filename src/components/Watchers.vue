<script setup>
import { ref, watch } from "vue";

const test = ref("");
// const ****= ref("")dp **** 여길 스테이트라고 부른다
const testErrorMsg = ref("");
// Watchers
const testColor = ref("");

watch(test, (val) => {
  // watch(지켜볼대상,값이 바뀌었을때 실행할 함수(빠뀐후 값/바뀌기 전 값)=>{})
  // 테스트 대상을 val값(ref)가져와서 실행하는함수???
  const pattern = /^[a-zA-Z]+$/;
  //  저장할 공간
  // 뉴에이트
  //리젝스 제한을 1.한글 완성글자만 허용 2.2~20자 제한 을 한다하면-> ^[가-힣]{2,20}$...너무빨리지움힝..;ㅅ;
  // 리젝스는 허용할 글자만 하는게 편하다 제외는 불편함이 많음.
  if (val === "") {
    testErrorMsg.value = "";
    // 여기에 벨류를 안넣으면 상수로써 적용이되어서 바꿀수없는값이 된다.
  } else if (pattern.test(val)) {
    // 우리가 작성한 test랑 여기 test다르다. (리젝트객체에있는 tset다)
    //스코프에 대해 자세히 다시 알아보기 기억에 안남음
    testErrorMsg.value = "O";
    testColor.value = "color : green;";
  } else {
    testErrorMsg.value = "X";
    testColor.value = "color : red;";
  }
});
</script>

<template>
  <h2>Watchers: 감시자</h2>

  <input type="text" v-model="test" />
  <!-- v-model 변수명 잘 정해야한다고함 -->
  <p :style="testColor">{{ testErrorMsg }}</p>
  <!-- inlin스타일로 한번 해보기 이제 이걸 동적으로 변경할려면 데이터바인딩을해줘야함
   testColor를  만들어줘야함 -->
</template>

<style></style>

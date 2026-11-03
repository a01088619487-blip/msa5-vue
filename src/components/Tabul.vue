<script setup>
import { ref } from "vue";
const flg1 = ref(false);
const flg2 = ref(false);
const flg3 = ref(false);

// 다른분에게 도움받은 방법
const profile = () => {
  flg1.value = true;
  flg2.value = false;
  flg3.value = false;
};

const settings = () => {
  flg1.value = false;
  flg2.value = true;
  flg3.value = false;
};

const bulletin = () => {
  flg1.value = false;
  flg2.value = false;
  flg3.value = true;
};
</script>

<template>
  <h2>Tab Ul</h2>
  <div class="all-tab">
    <div class="profile-tab">
      <button @click="profile">프로필</button>
    </div>
    <div class="settings-tab">
      <button @click="settings">설정</button>
    </div>
    <div class="bulletin-tab">
      <button @click="bulletin">게시판</button>
    </div>

    <div class="textbox">
      <p v-if="flg1">프로필 페이지 입니다.</p>
      <p v-if="flg2">설정 페이지 입니다.</p>
      <p v-if="flg3">게시판 페이지 입니다.</p>
    </div>
  </div>
</template>

<!-- Profile,Settings,Bulletin -->

<style scoped>
.all-tab {
  display: flex;
  justify-content: center;
}
button {
  background-color: rgb(247, 247, 247);
  border-radius: 15px;
}
.textbox {
  display: block;
}
</style>

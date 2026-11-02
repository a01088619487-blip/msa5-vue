<script setup>
import { ref } from "vue";
const allTab = ref("");
</script>

<template>
  <h2>Tab Ul</h2>
  <!-- Profile,Settings,Bulletin -->
  <div class="all-tab">
    <div class="tab-buttons">
      <button @click="allTab = 'profile'">프로필</button>
      <button @click="allTab = 'settings'">설정</button>
      <button @click="allTab = 'bulletin'">게시판</button>
    </div>

    <div class="textbox">
      <p v-if="allTab === 'profile'">프로필 페이지 입니다.</p>
      <p v-else-if="allTab === 'settings'">설정 페이지 입니다.</p>
      <p v-else-if="allTab === 'bulletin'">게시판 페이지 입니다.</p>
      <p v-else>버튼을 클릭해주세요.</p>
    </div>
  </div>
</template>

<style>
button {
  background-color: rgb(247, 247, 247);
  border-radius: 15px;
}
</style>

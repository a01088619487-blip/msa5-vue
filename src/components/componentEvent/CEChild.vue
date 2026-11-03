<script setup></script>
<template>
  <h2>CE Child</h2>
  <button @click="$emit('addCount')">add</button>
  <!-- $emit이 부모에게 가져오는 변수를 호출하겟다.-->
  <button @click="$emit('multiCount', 2)">multiCount</button>
</template>
<style scoped></style>

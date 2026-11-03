<script setup>
const props = defineProps({
  item: Object,
  str: String,
});
</script>

<template>
  <h2>Child</h2>
  <p>{{ props.item.username }}</p>
</template>

<style></style>

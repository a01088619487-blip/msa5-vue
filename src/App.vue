<script setup>
import CardList from "./components/CardList.vue";
import CEParent from "./components/componentEvent/CEParent.vue";
import ConditionalRendering from "./components/ConditionalRendering.vue";
import DataBinding from "./components/DataBinding.vue";
import LifeCycle from "./components/LifeCycle.vue";
import ListRendering from "./components/ListRendering.vue";
import Parent from "./components/props/Parent.vue";
import SlotParent from "./components/slot/SlotParent.vue";
import Tabul from "./components/Tabul.vue";
import Watchers from "./components/Watchers.vue";
</script>

<template>
  <h1>APP Component</h1>
  <!-- <data-binding></data-binding> -->
  <!-- 이렇게 적어두면 내가 적은 데이타를 불러올수잇다! 
   <data-binding/>    (HTML문법임) 
   이렇게 적어도 열고 닫기 기능이 있어 가능하다-->

  <!-- 새로운 컴포넌트 만들꺼에오 -->
  <!-- <ConditionalRendering /> -->

  <!-- 리스트 랜더링 -->
  <!-- <ListRendering></ListRendering> -->
  <!-- 탭Ul -->
  <!-- <Tabul /> -->
  <!-- Watchers -->
  <!-- <Watchers></Watchers> -->
  <!-- 먼저 Watchers 적고 나면 import로도 자동으로 잡아준다. -->
  <!-- <Parent /> -->
  <!-- <SlotParent></SlotParent> -->
  <!-- <CEParent></CEParent> -->
  <!-- <LifeCycle /> -->
  <CardList />
</template>

<style></style>

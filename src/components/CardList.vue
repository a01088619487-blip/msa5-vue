<script setup>
import axios from "axios";
import { onBeforeMount, ref } from "vue";

//변수 선언
const cards = ref([]);
// 리스트형식은 배열에 보내라
const page = ref(1);
const limit = 3;
// let limit는  안하는이유가 재할달을 할수있기 때문에

//함수선언
const getNextPage = async () => {
  try {
    const url = "https://picsum.photos/v2/list";
    const config = {
      params: {
        page: page.value,
        limit,
      },
    };
    const response = await axios.get(url, config);
    cards.value.push(...response.data);

    page.value++;
  } catch (error) {
    console.error(error);
  }
};
// 리섹버튼 리셋은 함수 정의다.
const reset = () => {
  //리셋할때 사진이 다시 3장 나오게 만들기
  // 1첫번째  방법 -이방법은네트워크 프로텍이?? 많아서 줄이고싶을때는
  //이건 다시 화면을 불러오는 방식이라 로딩이 있다.
  //cards.value = [];
  //page.value = 1;
  //getNextPage();

  //2번째 방법 -유저입장은 편하다 화면 다시가져올때 턴이 없다.
  //속도 빠름
  cards.value = cards.value.slice(0, limit);
  //slice특정위치에서 잘라서 쓰는
  //splice 도 가능하지만 원본이 바뀌는 위험이 있음.
  //cards.value = cards.value.splice(limit, cards.value.length-limit);
  page.value = 2;
  //왜 여긴 페이지가 2인지..설명해줫는데 모르겟네 ;ㅅ;..
};

//라이프 사이클 훅스
onBeforeMount(async () => {
  //비동기처리라서 동기처리로 변경해줘야함
  try {
    const url = "https://picsum.photos/v2/list";
    const config = {
      params: {
        page: page.value,
        limit,
      },
    };
    const response = await axios.get(url, config);
    cards.value.push(...response.data);

    page.value++;
  } catch (error) {
    console.error(error);
  }
});

// onBeforeMount(getNextPage); 기능 써볼려고 써본거임 ㅇ..ㅇ
</script>

<template>
  <div class="card-container">
    <div v-for="item in cards" :key="item.id" class="card">
      <div
        class="card-img"
        :style="{ backgroundImage: `url(${item.download_url})` }"
      ></div>
      <div class="card-text">{{ item.id }}: {{ item.author }}</div>
    </div>
  </div>
  <div>
    <button @click="getNextPage">다음페이지</button>
    <button @click="reset">리셋</button>
  </div>
</template>

<style scoped>
.card-container {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 10px;
}
.card {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.card-img {
  aspect-ratio: 4/3;
  /* aspect-ratio 보단패딩탑으로 주는게좋다고함  */
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}
</style>

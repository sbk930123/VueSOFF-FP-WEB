<template>
  <NavBar />
  <MainContent />
</template>

<script>
import NavBar from './components/NavBar.vue';
import MainContent from './components/MainContent.vue';

export default {
  name: 'App',
  components: {
    NavBar,
    MainContent
  }
}
</script>

<style>
* {
  font-family: 'SF-Pro-Display-Regular', 'AppleSDGothicNeoM';
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

a {
  /* 기본 스타일 속성 제거 */
  text-decoration: none; /* 밑줄 제거 */
  color: inherit; /* 기본 텍스트 색상 상속 */
  cursor: pointer; /* 커서 스타일 변경 */
}

body {
  background-color: #e9e9e9;
}

@font-face {
  font-family: 'SF-Pro-Display-Regular';
  src: url('../public/fonts/SF-Pro-Display-Regular.woff') format('woff');
  /* 필요한 경우 추가적인 폰트 속성을 여기에 지정할 수 있습니다 */
}

@font-face {
  font-family: 'AppleSDGothicNeoM';
  src: url('../public/fonts/AppleSDGothicNeoM.woff') format('woff');
  /* 필요한 경우 추가적인 폰트 속성을 여기에 지정할 수 있습니다 */
}
</style>

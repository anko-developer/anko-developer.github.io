<template>
  <div id="app">
    <router-view></router-view>
  </div>
</template>

<style>
  body {
    margin: 0;
    padding: 0;
    font-family: "Pretendard";
    font-size: 14px;
  }

  ul {
    margin: 0;
    padding: 0;
    list-style: none;
  }

  @import url('https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@100;300;400;500;700;900&display=swap');

  @font-face {
    font-family: "Pretendard";
    font-weight: 900;
    font-display: swap;
    src: local("Pretendard Black"),
        url("./assets/fonts/pretendard/Pretendard-Black.woff2") format("woff2");
  }

  @font-face {
    font-family: "Pretendard";
    font-weight: 800;
    font-display: swap;
    src: local("Pretendard ExtraBold"),
        url("./assets/fonts/pretendard/Pretendard-ExtraBold.woff2") format("woff2");
  }

  @font-face {
    font-family: "Pretendard";
    font-weight: 700;
    font-display: swap;
    src: local("Pretendard Bold"),
        url("./assets/fonts/pretendard/Pretendard-Bold.woff2") format("woff2");
  }

  @font-face {
    font-family: "Pretendard";
    font-weight: 600;
    font-display: swap;
    src: local("Pretendard SemiBold"),
        url("./assets/fonts/pretendard/Pretendard-SemiBold.woff2") format("woff2");
  }

  @font-face {
    font-family: "Pretendard";
    font-weight: 500;
    font-display: swap;
    src: local("Pretendard Medium"),
        url("./assets/fonts/pretendard/Pretendard-Medium.woff2") format("woff2");
  }

  @font-face {
    font-family: "Pretendard";
    font-weight: 400;
    font-display: swap;
    src: local("Pretendard Regular"),
        url("./assets/fonts/pretendard/Pretendard-Regular.woff2") format("woff2");
  }

  @font-face {
    font-family: "Pretendard";
    font-weight: 300;
    font-display: swap;
    src: local("Pretendard Light"),
        url("./assets/fonts/pretendard/Pretendard-Light.woff2") format("woff2");
  }

  @font-face {
    font-family: "Pretendard";
    font-weight: 200;
    font-display: swap;
    src: local("Pretendard ExtraLight"),
        url("./assets/fonts/pretendard/Pretendard-ExtraLight.woff2") format("woff2");
  }

  @font-face {
    font-family: "Pretendard";
    font-weight: 100;
    font-display: swap;
    src: local("Pretendard Thin"),
        url("./assets/fonts/pretendard/Pretendard-Thin.woff2") format("woff2");
  }
</style>
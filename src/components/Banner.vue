<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="banner">
    <div>
      <p class="subtitle-1">赫綵學員專屬</p>
      <h1><img src="../assets/img/banner/banner_title_txt.svg" alt="超高效設計學習術" /></h1>
      <p class="subtitle-2">朝目標精準努力 學習成果<span>加倍放大</span></p>
      <img
        src="../assets/img/banner/banner_icon.svg"
        alt="obo個別指導 X OKBOM線上學習 X appedu設計進階課程"
      />
    </div>
  </div>
</template>

<style lang="scss">
.banner {
  @include partSetting;
  // justify-content: normal;
  @include size(100%);
  min-height: 100vh;
  display: flex;
  align-items: center;
  position: relative;
  background: url('../assets/img/banner/banner_bg.png') no-repeat center/cover;
  overflow: hidden;
  > div {
    @include maxWidthArticle;
    p {
      color: white;
      background-color: black;
      font-weight: 600;
      display: inline-block;
      &:first-of-type {
        padding: 4.5px 14px;
        margin-bottom: 30px;
        @media screen and (max-width: 576px) {
          padding: 4.5px 11px;
          margin-bottom: 25px;
        }
      }
      &:last-of-type {
        margin-bottom: 70px;
        // padding: 4.5px 14px 4.5px 100vw;
        clip-path: polygon(0 0, 100% 0%, 75% 100%, 0% 100%);
        @media screen and (max-width: 768px) {
          margin-bottom: 90px;
        }
        @media screen and (max-width: 576px) {
          margin-bottom: 110px;
        }
        span {
          font-size: 32px;
          font-weight: inherit;
          color: $P2;
        }
      }
    }
    h1 {
      margin-bottom: 45px;
      img {
        @include size(415px, auto);
      }
      @media screen and (max-width: 576px) {
        margin-bottom: 55px;
        img {
          width: 100%;
        }
      }
    }
    > img {
      @include size(384px, auto);
      display: block;
      @media screen and (max-width: 576px) {
        width: 100%;
      }
    }
  }
}
</style>
<script></script>

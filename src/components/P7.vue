<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="p7">
    <article>
      <div><img src="../assets/img/P4/S3/P4S3_img.jpg" /></div>
      <div>
        <h2><span>100% 突破</span><br />你的學習瓶頸</h2>
        <a class="btn btn-1" href="#form">立即預約諮詢</a>
      </div>
    </article>
  </div>
</template>

<style lang="scss">
.p7 {
  @include partSetting;
  background: url('../assets/img/P4/P4_bg.svg') repeat center/1439.5px;
  > article {
    @include maxWidthArticle;
    display: flex;
    align-items: center;
    justify-content: space-between;
    > div {
      &:first-of-type {
        width: calc(50% - 24px);
        border-radius: 8px;
        overflow: hidden;
        display: flex;
        justify-content: center;
        align-items: center;
        box-shadow: 0px 4px 32px 0px rgba(0, 0, 0, 0.25);
        img {
          object-fit: cover;
          @include size(100%, auto);
        }
      }
      &:last-of-type {
        width: calc(50% - 50px);
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        gap: 80px;
        h2 {
          color: $P1;
          font-size: 65px;
          font-style: oblique;
          letter-spacing: 1.5px;
          line-height: 115%;
          span {
            font-size: 62px;
            font-weight: 600;
          }
        }
        a {
          background-color: $P1;
          color: white;
          padding: 10px 20px 11px;
          box-shadow: 0px 4px 32px 0px rgba(0, 0, 0, 0.25);
          &:hover {
            background-color: $P6;
          }
          &:disabled {
            background-color: $G10;
          }
        }
      }
    }
    @media screen and (max-width: 768px) {
      flex-direction: column;
      gap: 30px;
      > div {
        &:first-of-type {
          width: 100%;
        }
        &:last-of-type {
          width: 100%;
          flex-direction: row;
          align-items: center;
          justify-content: space-between;
          gap: 0px;
          h2 {
            font-size: 50px;
            line-height: 120%;
            span {
              font-size: 48px;
            }
          }
          a {
            padding: 8px 9px 9px;
          }
        }
      }
    }
    @media screen and (max-width: 576px) {
      flex-direction: column;
      gap: 30px;
      > div {
        &:last-of-type {
          h2 {
            font-size: 24px;
            line-height: 130%;
            span {
              font-size: 23px;
            }
          }
        }
      }
    }
  }
}
</style>

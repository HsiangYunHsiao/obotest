<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="p5" id="form">
    <article>
      <p>赫綵學員專屬 全方位學習整合</p>
      <h2>填表即可獲得個人專屬學習規劃</h2>
    </article>
    <article>
      <div>
        <div>
          <h3>雙重學習好禮填表送</h3>
          <p>贈品數量有限，送完為止</p>
        </div>
        <div>
          <div><p>個人專屬學習規劃</p></div>
          <div><p>180 堂線上設計課程</p></div>
        </div>
      </div>

      <receiveForm></receiveForm>
    </article>
  </div>
</template>

<style lang="scss">
.p5 {
  @include partSetting;
  background: $P1;
  > article {
    @include maxWidthArticle;
    &:first-of-type {
      text-align: center;
      margin-bottom: 50px;
      p {
        font-size: 32px;
        color: white;
        font-weight: 600;
        margin-bottom: 20px;
      }
      h2 {
        font-size: 40px;
        color: $P2;
        font-weight: 600;
      }
      @media screen and (max-width: 576px) {
        p {
          font-size: 16px;
          margin-bottom: 8px;
        }
        h2 {
          font-size: 20px;
        }
      }
    }
    &:last-of-type {
      display: flex;
      justify-content: space-between;
      align-items: center;
      > div {
        height: fit-content;
        width: calc(50% - 12px);
        border-radius: 8px;
        background-color: white;
        padding: 24px;
        display: flex;
        flex-direction: column;
        justify-content: center;
        box-shadow: 0px 4px 32px 0px rgba(0, 0, 0, 0.25);
        > div {
          &:first-of-type {
            color: $P5;
            text-align: center;
            margin-bottom: 24px;
            h3 {
              font-size: 24px;
              font-weight: 600;
              margin-bottom: 12px;
            }
            p {
              font-size: 15px;
              font-weight: 500;
            }
          }
          &:last-of-type {
            display: flex;
            justify-content: space-between;
            > div {
              height: 258px;
              width: calc(50% - 12px);
              padding: 15px;
              display: flex;
              flex-direction: column-reverse;
              align-items: center;
              &:first-of-type {
                background: url('../assets/img/P5/form/P5_image_01.png') no-repeat center/cover;
              }
              &:last-of-type {
                background: url('../assets/img/P5/form/P5_image_02.png') no-repeat center/cover;
              }
              > p {
                font-size: 18px;
                font-weight: 700;
                color: white;
                background-color: $P5;
                padding: 10px 12px 12px;
                border-radius: 8px;
                width: 100%;
                text-align: center;
              }
            }
          }
        }
      }
      > article {
        width: calc(50% - 12px);
      }
    }
  }
}
</style>

<script>
import receiveForm from './form.vue'
// import receiveForm from './AppeduForm.vue'

export default {
  components: { receiveForm }
}
</script>

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
    <article>
      <h2><span>200+</span> 以上 業界設計師實戰教學<br />手把手傳授經驗，讓你學習不走彎路</h2>
    </article>
    <article id="instructor" :style="insturctorStyles">
      <img src="../assets/img/P5/instructor/bg_teachers.png" alt="業界設計師圖片" />
    </article>
  </div>
</template>

<style lang="scss">
.p5 {
  @include partSetting;
  background: $P1;
  padding-bottom: 0px;
  position: relative;
  z-index: 1;
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
        letter-spacing: 1px;
      }
      h2 {
        font-size: 40px;
        color: $P2;
        font-weight: 600;
        letter-spacing: 1px;
      }
      @media screen and (max-width: 768px) {
        h2 {
          font-size: 36px;
        }
      }
      @media screen and (max-width: 576px) {
        margin-bottom: 22px;
        p {
          font-size: 16px;
          margin-bottom: 8px;
        }
        h2 {
          font-size: 20px;
        }
      }
    }
    &:nth-child(2) {
      display: flex;
      justify-content: space-between;
      align-items: center;
      > div {
        height: fit-content;
        width: calc(50% - 12px);
        border-radius: 8px;
        background-color: white;
        padding: 24px 2%;
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
              letter-spacing: 1.6px;
            }
            p {
              font-size: 15px;
              font-weight: 500;
              letter-spacing: 0.5px;
            }
            @media screen and (max-width: 576px) {
              h3 {
                font-size: 18px;
              }
              p {
                font-size: 13px;
              }
            }
          }
          &:last-of-type {
            display: flex;
            justify-content: space-between;
            > div {
              @include size(48%, 258px);
              max-width: 258px;
              padding: 15px;
              display: flex;
              flex-direction: column-reverse;
              align-items: center;
              border-radius: 8px;
              &:first-of-type {
                background: url('../assets/img/P5/form/P5_image_01.png') no-repeat center/cover;
              }
              &:last-of-type {
                background: url('../assets/img/P5/form/P5_image_02.png') no-repeat center/cover;
              }
              > p {
                font-size: 18px;
                font-weight: 700;
                letter-spacing: 1px;
                line-height: 120%;
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
      @media screen and (max-width: 768px) {
        flex-direction: column;
        gap: 22px;
        > div {
          width: 100%;
          padding: 24px 3.66%;
          > div {
            &:last-of-type {
              > div {
                height: 292px;
                max-width: 292px;
              }
            }
          }
        }
        > article {
          width: 100%;
        }
      }
      @media screen and (max-width: 576px) {
        flex-direction: column;
        gap: 22px;
        > div {
          padding: 12px 3.5%;
          > div {
            &:first-of-type {
              margin-bottom: 14px;
            }
            &:last-of-type {
              > div {
                height: 144px;
                max-width: 292px;
                padding: 6px;
                > p {
                  font-size: 13px;
                  letter-spacing: 0.5px;
                  padding: 8px 8px 8.6px;
                }
              }
            }
          }
        }
        > article {
          width: 100%;
        }
      }
    }
    &:nth-child(3) {
      margin: 125px 0 60px;
      h2 {
        font-size: 40px;
        color: white;
        font-weight: 600;
        text-align: center;
        line-height: 150%;
        letter-spacing: 1px;
        span {
          font-size: 57px;
          color: $P2;
          font-weight: 900;
        }
      }
      @media screen and (max-width: 768px) {
        margin: 50px 0 35px;
        h2 {
          font-size: 32px;
          span {
            font-size: 36px;
          }
        }
      }
      @media screen and (max-width: 576px) {
        margin: 52px 0 18px;
        h2 {
          font-size: 16px;
          span {
            font-size: 22px;
          }
        }
      }
    }
    &:last-of-type {
      position: relative;
      img {
        @include size(100vw, auto);
        position: absolute;
        left: calc(50% - 50vw);
        right: calc(50% - 50vw);
      }
    }
  }
}
</style>

<script>
import receiveForm from './form.vue'
// import receiveForm from './AppeduForm.vue'

export default {
  components: { receiveForm },
  data() {
    return {
      insturctorStyles: {
        height: '0px'
      }
    }
  },
  mounted() {
    window.addEventListener('resize', this.handleResize)
    window.onload = () => {
      this.handleResize()
    }
  },
  beforeUpdate() {},
  destroyed() {
    window.removeEventListener('resize', this.handleResize)
  },
  methods: {
    handleResize() {
      const theSize = document.querySelector('#instructor img')
      this.insturctorStyles.height = theSize.offsetHeight + 'px'
    }
  }
}
</script>

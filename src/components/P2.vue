<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="p2">
    <article>
      <div>
        <div>
          <p
            class="time_2"
            data-aos="fade-zoom-in"
            data-aos-easing="ease-in-back"
            data-aos-delay="800"
            data-aos-offset="0"
          >
            <img src="../assets/img/P2/emoji.svg" alt=">.<" />上課好想問問題，但又怕耽誤大家時間！
          </p>
          <p
            class="time_3"
            data-aos="fade-zoom-in"
            data-aos-easing="ease-in-back"
            data-aos-delay="1100"
            data-aos-offset="0"
          >
            <img
              src="../assets/img/P2/emoji.svg"
              alt="哭臉"
            />一坐到書桌就提不起勁，好想要有人幫忙我！
          </p>
        </div>
        <div>
          <p
            class="time_1"
            data-aos="fade-zoom-in"
            data-aos-easing="ease-in-back"
            data-aos-delay="300"
            data-aos-offset="0"
          >
            <img src="../assets/img/P2/emoji.svg" alt=">.<" />工作很忙，沒有時間上課怎麼辦？
          </p>
        </div>
        <div>
          <p
            class="time_3"
            data-aos="fade-zoom-in"
            data-aos-easing="ease-in-back"
            data-aos-delay="1100"
            data-aos-offset="0"
          >
            <img
              src="../assets/img/P2/emoji.svg"
              alt=">.<"
            />總是實戰時才遇到問題！好想要趕快有人替我解答！
          </p>
          <p
            class="time_2"
            data-aos="fade-zoom-in"
            data-aos-easing="ease-in-back"
            data-aos-delay="800"
            data-aos-offset="0"
          >
            <img
              src="../assets/img/P2/emoji.svg"
              alt=">.<"
            />課程好難！但是同學又好厲害，好害怕跟不上大家！
          </p>
        </div>
      </div>
    </article>
    <div
      class="time_3"
      data-aos="fade-zoom-in"
      data-aos-easing="ease-in-back"
      data-aos-delay="1200"
      data-aos-offset="0"
    ></div>
    <div
      class="time_3"
      data-aos="fade-zoom-in"
      data-aos-easing="ease-in-back"
      data-aos-delay="1200"
      data-aos-offset="0"
    ></div>
    <div
      class="time_3"
      data-aos="fade-zoom-in"
      data-aos-easing="ease-in-back"
      data-aos-delay="1200"
      data-aos-offset="0"
    ></div>
    <div
      class="time_3"
      data-aos="fade-zoom-in"
      data-aos-easing="ease-in-back"
      data-aos-delay="1200"
      data-aos-offset="0"
    ></div>
  </div>
</template>

<style lang="scss">
.p2 {
  @include partSetting;
  position: relative;
  background: $P1;
  background: linear-gradient(
    180deg,
    rgba(2, 88, 173, 1) 0%,
    rgba(14, 108, 200, 1) 95%,
    rgba(15, 109, 202, 1) 100%
  );

  article {
    @include maxWidthArticle;

    > div {
      &:first-of-type {
        position: relative;
        z-index: 2;
        display: flex;
        flex-direction: column;
        gap: 48px;
        @media screen and (max-width: 768px) {
          gap: 66px;
        }
        @media screen and (max-width: 576px) {
          gap: 50px;
        }
        > div {
          display: flex;
          flex-direction: row;
          justify-content: center;
          > p {
            @include size(fit-content);
            color: black;
            font-weight: 600;
            background-color: white;
            display: flex;
            align-items: center;
            gap: 7px;
            border-radius: 8px;
            position: relative;
            &.time_1 {
              font-size: 36px;
              line-height: 49.03px;
              padding: 16px;
              > img {
                @include size(48px);
              }
            }
            &.time_2 {
              font-size: 24px;
              line-height: 32.69px;
              padding: 12px;
              > img {
                @include size(36px);
              }
            }
            &.time_3 {
              font-size: 16px;
              line-height: 21.79px;
              padding: 8px 12px;
              > img {
                @include size(24px);
              }
            }
            &::before {
              content: '';
              position: absolute;
              @include size(50px, 28px);
              background: url('../assets/img/P2/polygon.svg') no-repeat center/contain;
              bottom: -18px;
              right: 15px;
            }
          }
          &:first-of-type {
            gap: 35px;
            p {
              &:last-of-type {
                transform: translateY(28px);
              }
            }
          }
          &:nth-child(2) {
          }
          &:nth-child(3) {
            gap: 42px;
            p {
              &:first-of-type {
                transform: translateY(-4px);
              }
            }
          }
          @media screen and (max-width: 768px) {
            flex-direction: column;
            &:first-of-type {
              gap: 5px;
              > p {
                &:last-of-type {
                  align-self: flex-end;
                }
              }
            }
            &:nth-child(2) {
              > p {
                margin-left: 10px;
              }
            }
            &:nth-child(3) {
              gap: 28px;
              transform: translateY(-18px);
              > p {
                &:last-of-type {
                  align-self: flex-end;
                }
              }
            }
          }
          @media screen and (max-width: 576px) {
            &:first-of-type {
              gap: 0px;
              > p {
                &:last-of-type {
                  align-self: flex-end;
                }
              }
            }
            &:nth-child(2) {
              > p {
                margin-left: 10px;
              }
            }
            &:nth-child(3) {
              gap: 15px;
              transform: translateY(-25 px);
              > p {
                &:last-of-type {
                  align-self: flex-end;
                }
              }
            }
            > p {
              gap: 5.5px;
              &.time_1 {
                font-size: 18.63px;
                line-height: 25.37px;
                padding: 8.25px;
                > img {
                  @include size(24.84px);
                }
              }
              &.time_2 {
                font-size: 11.88px;
                line-height: 16.19px;
                padding: 5.94px;
                > img {
                  @include size(17.83px);
                }
              }
              &.time_3 {
                font-size: 11.11px;
                line-height: 15.13px;
                padding: 5.74px;
                > img {
                  @include size(15.75px);
                }
              }
              &::before {
                content: '';
                position: absolute;
                @include size(25.87px, 16px);
                background: url('../assets/img/P2/polygon.svg') no-repeat center/cover;
                bottom: -10px;
                right: 15px;
              }
            }
          }
        }
      }
    }
  }
  > div {
    background: url('../assets/img/P2/question_blur_01.png') no-repeat center/cover;
    position: absolute;
    z-index: 1;
    &:nth-child(2) {
      @include size(386.46px, 56px);
      left: -43px;
      top: 40%;
    }
    &:nth-child(3) {
      @include size(333.99px, 47px);
      left: 10%;
      bottom: 12%;
    }
    &:nth-child(4) {
      @include size(386.46px, 52px);
      right: 22%;
      top: 10%;
    }
    &:nth-child(5) {
      @include size(386.46px, 52px);
      right: -50px;
      top: 40%;
    }
    @media screen and (max-width: 768px) {
      &:nth-child(2) {
        left: -12%;
        top: 26.5%;
      }
      &:nth-child(3) {
        left: -3%;
        bottom: 22%;
      }
      &:nth-child(4) {
        right: -52px;
        top: 6%;
      }
      &:nth-child(5) {
        right: -23%;
        top: 63%;
      }
    }
    @media screen and (max-width: 576px) {
      &:nth-child(2) {
        @include size(236.19px, 31.62px);
        top: 28.5%;
      }
      &:nth-child(3) {
        @include size(236.19px, 31.62px);
        left: -17%;
        bottom: 19%;
      }
      &:nth-child(4) {
        @include size(236.19px, 31.62px);
        right: -10%;
        top: 4%;
      }
      &:nth-child(5) {
        @include size(236.19px, 31.62px);
        top: 57%;
      }
    }
  }
}
</style>

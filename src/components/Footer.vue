<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="footer">
    <article>
      <section>
        <div>
          <a href="https://www.appedu.com.tw/" target="_blank"></a>
          <a class="get" href="#form">想了解課程</a>
        </div>
      </section>
      <section>
        <div>
          <p>100 台北市中正區忠孝西路ㄧ段6號16樓</p>
          <p>(02) 2388 - 6688 #8006 ｜ 平日 9:00 - 18:30</p>
          <p>appedu@appedu.com.tw</p>
        </div>
      </section>
      <section>
        <div>
          <ul>
            <li>
              <a href="https://www.facebook.com/appedu/" target="_blank"></a>
            </li>
            <li>
              <a href="https://page.line.me/ksn8716p?openQrModal=true" target="_blank"></a>
            </li>
            <li>
              <a href="https://www.youtube.com/user/AppeduDesignTraining" target="_blank"></a>
            </li>
            <li>
              <a href="https://www.instagram.com/appedudesign/" target="_blank"></a>
            </li>
          </ul>
          <p>Copyright ©Appedu. All rights reserved.</p>
          <p>赫綵電腦有限公司保有活動內容更改之權利，最新資訊以活動網站為主</p>
        </div>
      </section>
    </article>
  </div>
</template>

<style lang="scss">
footer {
  @include partSetting;
  padding: 50px 70px;
  background-color: $P2;
  .footer {
    @include maxWidthArticle;
    width: 100%;
    article {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      section {
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 10px 0;
        @media screen and (max-width: 996px) {
          border: none;
        }
        @media screen and (max-width: 576px) {
          text-align: center;
        }
        &:nth-of-type(1) {
          padding-right: 60px;
          max-width: 28%;
          border-right: 1px solid $S1;
          justify-content: flex-start;
          @media screen and (max-width: 996px) {
            width: 100%;
            max-width: 100%;
            border: none;
            justify-content: center;
            padding: 0 0 30px;
          }
          @media screen and (max-width: 576px) {
            width: 100%;
          }
          div {
            a {
              display: block;
              &:first-of-type {
                @include size(190px, 44px);
                background: url(../assets/img/normal_logo.svg) no-repeat center;
                background-size: contain;
                transition: all 0.3s ease;
                &:hover {
                  background-image: url(../assets/img/hover_logo.svg);
                }
              }
              &.get {
                width: 100%;
                color: white;
                border: 1px solid $T1;
                background-color: $S1;
                box-shadow: 4px 4px 0px 0px $T2;
                text-align: center;
                padding: 0.5em 0;
                font-weight: bolder;
                text-decoration: none;
                margin-top: 20px;
                transition: all 0.3s ease;
                &:hover {
                  background-color: $S3;
                }
                &:disabled {
                  background-color: $G7;
                  color: $T3;
                  border: none;
                }
              }
            }
          }
        }
        &:nth-of-type(2) {
          justify-content: center;
          @media screen and (max-width: 996px) {
            width: 50%;
            max-width: 50%;
            padding: 0 5% 0 0;
          }
          @media screen and (max-width: 576px) {
            width: 100%;
            max-width: 100%;
            padding: 0 0 30px;
          }
          p {
            margin: 10px 0;
            color: $S1;
          }
        }
        &:nth-of-type(3) {
          padding-left: 60px;
          max-width: 35%;
          border-left: 1px solid $S1;
          justify-content: flex-end;
          @media screen and (max-width: 996px) {
            width: 50%;
            max-width: 50%;
            padding: 0 0 0 5%;
          }
          @media screen and (max-width: 576px) {
            width: 100%;
            max-width: 100%;
            border: none;
            padding: 0;
            justify-content: center;
          }
          ul {
            display: flex;
            padding: 0;
            @media screen and (max-width: 576px) {
              justify-content: center;
            }
            li {
              list-style: none;
              margin-right: 10px;
              background-repeat: no-repeat;
              background-size: cover;
              &:nth-child(1) a {
                background-image: url(../assets/img/facebook.svg);
                &:hover {
                  background-image: url(../assets/img/facebook_hover.svg);
                }
              }
              &:nth-child(2) a {
                background-image: url(../assets/img/line.svg);
                &:hover {
                  background-image: url(../assets/img/line_hover.svg);
                }
              }

              &:nth-child(3) a {
                background-image: url(../assets/img/youtube.svg);
                &:hover {
                  background-image: url(../assets/img/youtube_hover.svg);
                }
              }
              &:nth-child(4) a {
                background-image: url(../assets/img/instgram.svg);
                &:hover {
                  background-image: url(../assets/img/instgram_hover.svg);
                }
              }
              a {
                border-radius: 4px;
                display: flex;
                @include size(30px);
                justify-content: center;
                align-items: center;
                transition: all 0.3s ease;
              }
            }
          }
          p {
            color: $S1;
            font-size: 14px;
            margin: 10px 0;
          }
        }
      }
    }
  }
}
</style>

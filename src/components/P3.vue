<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="p3">
    <article>
      <div></div>
      <div>
        <h3>
          在<span>學好設計</span>的這條路上<br />我們來幫你<span>解決可能遇到的問題</span> ...
        </h3>
      </div>
    </article>
    <article>
      <div>
        <div>
          <div><img src="../assets/img/P3/P3_01.png" alt="無法配合長時數課程" /></div>
          <div>
            <h3 class="subtitle-1">無法配合長時數課程</h3>
          </div>
        </div>
        <img src="../assets/img/P3/P3_icon.svg" alt="三角形符號" />
        <div>
          <div>
            <img src="../assets/img/icon/title_1.svg" alt="1" />
            <h4 class="subtitle-1">進度制彈性學習機制</h4>
          </div>
          <p class="body-3">時數自由選、學習方式彈性高！</p>
        </div>
      </div>
      <div>
        <div>
          <div><img src="../assets/img/P3/P3_02.png" alt="希望課後有專人指導" /></div>
          <div>
            <h3 class="subtitle-1">希望課後有專人指導</h3>
          </div>
        </div>
        <img src="../assets/img/P3/P3_icon.svg" alt="三角形符號" />
        <div>
          <div>
            <img src="../assets/img/icon/title_2.svg" alt="2" />
            <h4 class="subtitle-1">專業講師私人教練式指導</h4>
          </div>

          <p class="body-3">解決職場中或學習上的疑難雜症！</p>
        </div>
      </div>
      <div>
        <div>
          <div><img src="../assets/img/P3/P3_03.png" alt="跟課堂進度覺得吃力" /></div>
          <div>
            <h3 class="subtitle-1">跟課堂進度覺得吃力</h3>
          </div>
        </div>
        <img src="../assets/img/P3/P3_icon.svg" alt="三角形符號" />
        <div>
          <div>
            <img src="../assets/img/icon/title_3.svg" alt="3" />
            <h4 class="subtitle-1">學習目標明確的差異化教學</h4>
          </div>

          <p class="body-3">高效速成，讓你所學及所用！</p>
        </div>
      </div>
    </article>
    <div>
      <h4>
        <span>客製化你的學習需求，<br />掌握痛點才能<span>對症下藥！</span></span>
      </h4>
    </div>
  </div>
</template>

<style lang="scss">
.p3 {
  @include partSetting;
  padding-bottom: 0px !important;
  background-color: $P1;
  article {
    @include maxWidthArticle;
    display: flex;
    gap: 25px;
    &:first-of-type {
      width: 100%;
      margin-bottom: 80px;
      > div {
        &:first-of-type {
          @include size(132px);
          background: url('../assets/img/P3/search_icon.svg') no-repeat center/contain;
        }
        &:last-of-type {
          h3 {
            font-weight: 600;
            color: white;
            font-size: 40px;
            line-height: 150%;
            letter-spacing: 1px;
            span {
              font-weight: inherit;
              color: $P2;
              font-size: 48px;
              padding: 0 6px;
              &:last-of-type {
                padding-bottom: 12px;
                background: url(/Event/test/obo/src/assets/img/P3/P3_underline_b.svg) no-repeat
                  bottom/contain;
              }
            }
          }
        }
      }
      @media screen and (max-width: 768px) {
        gap: 20px;
        flex-direction: column;
        margin-bottom: 60px;
        > div {
          &:first-of-type {
            @include size(88px);
          }
          &:last-of-type {
            h3 {
              font-size: 32px;

              span {
                font-size: 36px;
                &:last-of-type {
                  padding-bottom: 6px;
                  background-image: url(/Event/test/obo/src/assets/img/P3/P3_underline_m.svg);
                }
              }
            }
          }
        }
      }
      @media screen and (max-width: 576px) {
        gap: 8px;
        margin-bottom: 25px;
        > div {
          &:first-of-type {
            @include size(44px);
          }
          &:last-of-type {
            h3 {
              font-size: 16px;

              span {
                font-size: 20px;
                &:last-of-type {
                  background-image: url(/Event/test/obo/src/assets/img/P3/P3_underline_s.svg);
                }
              }
            }
          }
        }
      }
    }
    &:last-of-type {
      flex-wrap: nowrap;
      justify-content: space-between;
      align-items: stretch;
      > div {
        width: calc(33.33% - 12px);
        color: $P1;
        display: flex;
        flex-direction: column;
        > div {
          text-align: center;
          box-shadow: 0px 4px 32px 0px rgba(0, 0, 0, 0.25);
          &:first-of-type {
            background-color: white;
            border-radius: 8px;
            overflow: hidden;
            img {
              @include size(100%, auto);
            }
            > div {
              &:last-of-type {
                padding: 12px 8% 15px;
                h3 {
                  line-height: 140%;
                }
              }
            }
          }
          &:last-of-type {
            text-align: left;
            background-color: white;
            border-radius: 8px;
            padding: 16px;
            flex: 1;
            @media screen and (max-width: 576px) {
              padding: 12px;
            }
            > div {
              display: flex;
              gap: 8px;
              margin-bottom: 12px;
              img {
                display: block;
                @include size(24px);
                margin-top: 6.5px;
              }
              h4 {
                line-height: 33px;
              }
            }
            p {
              line-height: 140%;
            }
          }
        }
        > img {
          margin: 16px auto;
          display: block;
          @include size(50px, auto);
          @media screen and (max-width: 576px) {
            margin: 8px auto;
          }
        }
      }
      @media screen and (max-width: 768px) {
        overflow-x: auto;
        display: flex;
        white-space: nowrap;
        gap: 24px;

        > div {
          width: 384px;
          min-width: 384px;
        }
      }
      @media screen and (max-width: 576px) {
        > div {
          width: 291px;
          min-width: 291px;
          > div {
            &:first-of-type {
              > div {
                &:last-of-type {
                  padding: 9px 2% 8px;
                }
              }
            }
            &:last-of-type {
              > div {
                margin-bottom: 5px;
              }
            }
          }
        }
      }
    }
  }
  > div {
    @include size(100%, 128px);
    margin-top: 100px;
    position: relative;

    h4 {
      @include size(100vw, 100%);
      background: url('../assets/img/P3/P3_bg.svg') repeat-x center/cover;
      position: absolute;
      left: calc(50% - 50vw);
      right: calc(50% - 50vw);
      display: flex;
      justify-content: center;
      align-items: center;
      br {
        display: none;
      }
      > span {
        color: white;
        font-size: 40px;
        font-weight: 600;
        display: block;
        width: 100%;
        text-align: center;
        line-height: 150%;
        > span {
          color: $P2;
          font-size: 48px;
          font-weight: inherit;
          border: 3px solid white;
          border-radius: 50%;
          padding: 0% 0.2% 0% 0.6%;
        }
      }
    }
    @media screen and (max-width: 1200px) {
      height: 155px;
      h4 {
        br {
          display: block;
        }
      }
    }
    @media screen and (max-width: 768px) {
      margin-top: 64px;
      h4 {
        left: calc(50% - 50vw - 2.5%);
        right: calc(50% - 50vw - 2.5%);
        > span {
          font-size: 32px;
          line-height: 170%;
          > span {
            font-size: 40px;
          }
        }
      }
    }
    @media screen and (max-width: 576px) {
      margin-top: 20px;
      height: 120px;
      h4 {
        > span {
          font-size: 16px;
          line-height: 200%;
          > span {
            font-size: 20px;
          }
        }
      }
    }
  }
  @media screen and (max-width: 768px) {
    // padding-left: 0;
    padding-right: 0;
    article {
      max-width: none;
      padding-left: calc(0.2% + 0.1vw);
      > div {
        &:last-of-type {
          margin-right: 24px;
        }
      }
    }
  }
}
</style>

<script></script>

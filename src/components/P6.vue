<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="p6">
    <div class="heading-1 width_border" id="p6">
      <div>
        <h2>品牌好口碑，學習有保障</h2>
        <p class="subtitle">成功培育超過千位優秀設計畢業生</p>
      </div>
    </div>
    <article>
      <div v-for="item in commentList" :key="item.name">
        <h4 :class="item.type">
          {{ item.name }} <span>{{ item.school }}</span>
        </h4>
        <p>
          {{ item.content }}
        </p>
      </div>
    </article>
  </div>
</template>
<style lang="scss">
.p6 {
  @include partSetting;
  position: relative;
  z-index: 2;
  background-color: #d5dee7;
  border: 1px solid $black;
  @media screen and (max-width: 996px) {
    background-size: 80%;
    background-position: bottom 20px left 20px;
  }
  @media screen and (max-width: 576px) {
    padding-right: 0;
    padding-left: 0;
  }
  .heading-1 {
    // position: absolute;
    top: -65px;
    @media screen and (max-width: 996px) {
      top: -54px;
    }
    @media screen and (max-width: 768px) {
      top: -44px;
    }
    @media screen and (max-width: 576px) {
      top: -42px;
    }
    > div {
      h2 {
        color: $S1;
      }
      p {
        color: $T1;
      }
    }
  }
  article {
    @include maxWidthArticle;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    @media screen and (max-width: 576px) {
      flex-wrap: nowrap;
      white-space: nowrap;
      overflow-x: auto;
      display: flex;
      margin: 0;
    }
    div {
      background-color: $P1;
      width: calc(100% / 4 - 20px);
      padding: 1.5em;
      box-shadow: 7px 7px 0 $T4;
      border: 1px solid $G1;
      margin: 20px 0;
      @media screen and (max-width: 1280px) {
        width: calc(100% / 2 - 20px);
      }
      @media screen and (max-width: 576px) {
        min-width: 80%;
        white-space: normal;
        display: inline-block;
        margin: 30px 10px;
      }
      h4 {
        padding-left: 2em;
        color: $S1;
        font-weight: bolder;
        font-size: 22px;
        letter-spacing: 0.1px;
        display: flex;
        justify-content: space-between;
        align-items: flex-end;
        position: relative;
        &:before {
          content: '';
          @include size(1.5em);
          position: absolute;
          background-size: contain;
          background-repeat: no-repeat;
          background-position: center;
          left: 0;
          bottom: 0;
        }
        span {
          color: $T3;
          font-weight: normal;
          font-size: 14px;
          text-align: right;
        }
        &.student1 {
          &::before {
            background-image: url(../assets/img/p6_profile01.svg);
          }
        }
        &.student2 {
          &::before {
            background-image: url(../assets/img/p6_profile02.svg);
          }
        }
        &.student3 {
          &::before {
            background-image: url(../assets/img/p6_profile03.svg);
          }
        }
        &.student4 {
          &::before {
            background-image: url(../assets/img/p6_profile04.svg);
          }
        }
      }
      p {
        font-size: 14px;
        color: $T2;
        margin: 1em 0;
        text-align: justify;
      }
    }
  }
}
</style>

<script>
export default {
  data() {
    return {
      commentList: [
        {
          type: 'student4',
          name: '王Ｏ綺',
          school: '台中學院',
          content:
            '這是第一次接觸PS這個軟體，雖然一開始對於軟體操作有許多不懂、不熟悉的地方，但經過課堂上的練習，讓我對PS更加熟悉，也學到很多電繪技巧以及風格的呈現方式，使我受益良多，相信在日後創作上也能夠更順利。'
        },
        {
          type: 'student3',
          name: '陳Ｏ君',
          school: '台中學院',
          content:
            '我很慶幸能夠來這裡上課，我從不會畫、沒想法等等到我能自己完成作品，那種感動是無法用言語形容但真切留在心中。我也很感謝老師的用心教導，私下問問題也都一一解決，給予我鼓勵。'
        },
        {
          type: 'student2',
          name: '黃Ｏ暐',
          school: '中壢學院',
          content:
            '謝謝老師用心手把手教學，因為工作時間不固定的關係經常請假，但回家用影片複習還是能理解好好練習，作業也能順利做完，老師也給了很多實用的回饋。雖然課程內容很緊湊，但上得很開心，謝謝老師豐富的課程安排！'
        },
        {
          type: 'student1',
          name: '洪Ｏ偉',
          school: '台中學院',
          content:
            '整體課程我覺得很適合新入繪圖圈的人，藉由額外發問從老師那學到更多延伸的技巧，總是想要學得更多。也感謝老師所教的小技巧還有我所不知道的透視算法，最後謝謝赫綵讓我認識那麼多繪圖的夥伴。'
        },
        {
          type: 'student1',
          name: '戴Ｏ克',
          school: '東區學院',
          content:
            '首次用繪圖板自己練習，完成完整的作品。感謝老師幫助我在控筆的方面找到確實的方法。此外，老師上色教得非常好，不過還是要自己多練習才能更精確，人物、材質、色調要多練才能體悟老說的話。'
        },
        {
          type: 'student2',
          name: '呂Ｏ廷',
          school: '站前學院',
          content:
            '老師的教學很有系統性，動植物都會以基礎知識開始。老師及學長都很親切，會給每個同學建議，還會補充額外教材，很感謝！'
        },
        {
          type: 'student4',
          name: '蔡Ｏ晏',
          school: '高雄學院',
          content:
            '老師教的內容很基礎，每週的作業也都可以訓練基礎。經過每週的作業練習讓我對一些自己不擅長的東西有了很明確的方向，不會像以前一樣不知道如何下手'
        },
        {
          type: 'student2',
          name: '陳Ｏ倫',
          school: '台中學院',
          content:
            '這幾週我學到了好多我之前都不知道的知識，尤其是透視！真的很感謝老師清楚明瞭的教學，希望之後還有更多交流的機會。'
        }
      ]
    }
  }
}
</script>

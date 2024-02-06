<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <article class="receiveForm">
    <form action="" class="form-distribution">
      <label for="userName" :class="{ error: verify.nameError && isSubmitted }">
        <input
          name=""
          type="text"
          id="userName"
          v-model="user.name"
          placeholder="真實姓名*"
          @input="checkInput()"
          :class="{ correct: !verify.nameError }"
          required
        />
        <span v-if="verify.nameError && isSubmitted">{{ verify.nameErrorMsg }}</span>
      </label>
      <label for="cellphone" :class="{ error: verify.cellphoneError && isSubmitted }">
        <input
          type="tel"
          id="cellphone"
          v-model="user.cellphone"
          placeholder="連絡電話*"
          inputmode="tel"
          @input="checkInput()"
          :class="{ correct: !verify.cellphoneError }"
          required
        />
        <span v-if="verify.cellphoneError && isSubmitted">{{ verify.cellphoneErrorMsg }}</span>
      </label>
      <label for="email" :class="{ error: verify.emailError && isSubmitted }">
        <input
          type="email"
          id="email"
          v-model="user.email"
          placeholder="E-mail*"
          inputmode="email"
          @input="checkInput()"
          :class="{ correct: !verify.emailError }"
          required
        />
        <span v-if="verify.emailError && isSubmitted">{{ verify.emailErrorMsg }}</span>
      </label>
      <div class="select" :class="{ error: verify.remarkError && isSubmitted }">
        <select
          name=""
          id=""
          required
          v-model="user.remark"
          @change="checkInput()"
          :class="{ correct: !verify.remarkError && user.remark != '' }"
        >
          <option value="" selected hidden>可聯繫時段*</option>
          <option value="上午09:00~12:00">上午 09:00~12:00</option>
          <option value="下午12:00~18:00">下午 12:00~18:00</option>
          <option value="晚間18:00~22:00">晚間 18:00~22:00</option>
          <option value="全時段皆可">全時段皆可</option>
        </select>
        <span v-if="verify.remarkError && isSubmitted">{{ verify.remarkErrorMsg }}</span>
      </div>
      <div class="select" :class="{ error: verify.cityError && isSubmitted }">
        <select
          name=""
          ref="city"
          v-model="user.city"
          required
          @change="getArea()"
          :class="{ correct: !verify.cityError && user.city != '' }"
        >
          <option value="" selected hidden>居住縣市*</option>
          <option :value="item.id" v-for="item in city" :key="item.id">
            {{ item.name }}
          </option>
        </select>
        <span v-if="verify.cityError && isSubmitted">{{ verify.cityErrorMsg }}</span>
      </div>
      <div class="select" :class="{ error: verify.areaError && isSubmitted }">
        <select
          name=""
          id=""
          v-model="user.area"
          required
          @change="checkInput()"
          :class="{ correct: !verify.areaError && user.area != '' }"
        >
          <option value="" selected hidden>居住區域*</option>
          <option :value="item.id" v-for="item in area" :key="item.id">{{ item.name }}</option>
        </select>
        <span v-if="verify.areaError && isSubmitted">{{ verify.areaErrorMsg }}</span>
      </div>
      <div class="select w-100" :class="{ error: verify.remark2Error && isSubmitted }">
        <select
          name=""
          id=""
          v-model="user.remark2"
          @change="checkInput()"
          :class="{ correct: !verify.remark2Error && user.remark2 != '' }"
        >
          <option value="" selected hidden>設計程度*</option>
          <option value="零基礎">零基礎</option>
          <option value="初學者">初學者</option>
          <option value="設計師">設計師</option>
        </select>
        <span v-if="verify.remark2Error && isSubmitted">{{ verify.remark2ErrorMsg }}</span>
      </div>
      <div class="checkbox" :class="{ error: verify.agreementError && isSubmitted }">
        <input
          type="checkbox"
          name=""
          id="agreement"
          v-model="user.agreement"
          @change="checkInput()"
        />
        <label for="agreement"
          >我已詳細閱讀並同意<a href="https://www.appedu.com.tw/frame-privacy" target="_blank"
            >隱私權使用條款</a
          ></label
        >
        <span v-if="verify.agreementError && isSubmitted">{{ verify.agreementErrorMsg }}</span>
      </div>
      <input class="btn" type="submit" value="立即送出" @click.prevent="sendForm()" />
    </form>
    <section class="complete" ref="formComplete">
      <div class="heading-1">
        <img src="../assets/img/popupLogo.svg" alt="" />
        <h3>感謝你給自己一個成長的機會！</h3>
        <p class="subtitle">後續將由專人盡快與您聯繫</p>
        <a href="https://www.appedu.com.tw/">確認</a>
      </div>
    </section>
  </article>
</template>

<style lang="scss">
article.receiveForm {
  background-color: $white;
  padding: 2%;
  max-width: 800px;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  width: 100%;
  border: 1px solid $G1;
  box-shadow: 7px 7px 0px $T2;
  @media screen and (max-width: 768px) {
    padding: 16px;
  }
  form {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    label {
      width: calc(50% - 10px);
      position: relative;
      margin: 1em 0;
      input:not([type='checkbox']) {
        width: 100%;
        padding: 5px 10px;
        font-size: 18px;
        background-color: $white;
        border: none;
        outline: 1px solid black;
        transition: all 0.3s ease;
        color: $T3;

        @media screen and (max-width: 576px) {
          font-size: 14px;
        }
        &:hover {
          background-color: $G8;
          color: $T2;
        }
        &::placeholder {
          color: $T3;
          transition: all 0.3s ease;
        }
        &:focus {
          color: $S1;
          outline: 2px solid $S1;
          &::placeholder {
            color: $S1;
          }
        }
        &:focus-visible {
          color: $S1;
          outline: 2px solid $S1;
        }
        &.correct {
          color: $T2;
        }
      }
      span {
        position: absolute;
        bottom: -1.8em;
        left: 0;
        color: $A1;
      }
      &.error {
        input {
          outline: 1px solid $A1;
          color: $A1;
          &::placeholder {
            color: $A1;
          }
        }
      }
      &:hover {
        input:not([type='checkbox']) {
          &::placeholder {
            color: $T2;
          }
        }
      }
    }

    .select {
      width: calc(50% - 10px);
      position: relative;
      margin: 1em 0;
      select {
        width: 100%;
        padding: 5px 10px;
        font-size: 18px;
        appearance: none;
        -moz-appearance: none;
        -webkit-appearance: none;
        background: url(../assets/img/select.svg) no-repeat;
        background-position: calc(100% - 10px) center;
        color: $T3;
        transition: all 0.3s ease;
        border: 1px solid #000;
        -webkit-border: 1px solid #000;
        background-color: $white;
        border: none;
        outline: 1px solid $black;
        @media screen and (max-width: 576px) {
          font-size: 14px;
        }
        &:hover {
          background-color: $G8;
          color: $T2;
        }
        &:focus {
          color: $S1;
          outline: 2px solid $S1;
          &::placeholder {
            color: $S1;
          }
        }
        &:focus-visible {
          color: $S1;
          outline: 2px solid $S1;
        }
        &.correct {
          color: $T2;
        }
      }
      span {
        position: absolute;
        bottom: -1.8em;
        left: 0;
        color: $A1;
      }
      &:hover {
        select {
          background-color: $G8;
        }
      }
      &.error {
        select {
          outline: 1px solid $A1;
          color: $A1;
          background-image: url(../assets/img/select-err.svg);
          position: relative;
        }
      }
    }
    .error {
      span {
        height: 15px;
        line-height: 15px;
        margin-left: 5px;
        position: absolute;
        bottom: -1.5em;
        left: 0;
        color: $A1;
        display: flex;
        align-items: center;
        &:before {
          content: '';
          background-image: url(../assets/img/Alert.svg);
          background-repeat: no-repeat;
          background-size: contain;
          background-position: left;
          display: inline-block;
          height: 100%;
          width: 26px;
        }
      }
    }
    .checkbox {
      position: relative;
      width: 100%;
      text-align: center;
      input[type='checkbox'] + label {
        color: $T2;
        font-size: 14px;
        margin: 1em auto;
        transition: all 0.3s ease;
        width: auto;
        padding-left: 1.5em;
        cursor: pointer;
        a {
          text-decoration: none;
          color: $S2;
        }
        &:hover {
          color: $T2;
        }
      }
      input[type='checkbox'] {
        display: none;
      }
      input[type='checkbox'] + label::before {
        content: '';
        position: absolute;
        @include size(1.2em);
        border: 1px solid $T1;
        left: 0;
        margin-top: 0.2em;
        border-radius: 50%;
      }
      input[type='checkbox']:hover + label:hover {
        color: $S1;
      }
      input[type='checkbox']:checked + label {
        color: $T2;
      }
      input[type='checkbox']:checked + label::before {
        box-shadow: 0.1em 0.1em 0 $white inset, -0.1em 0.1em 0 $white inset,
          0.1em -0.1em 0 $white inset, -0.1em -0.1em 0 $white inset, 1em 1em 0 $S1 inset;
      }
      span {
        width: 100%;
        bottom: -0.5em;
        justify-content: center;
      }
    }
    //
  }
  input[type='submit'] {
    background-color: $S1;
    border: 1px solid $T1;
    border-radius: 0;
    box-shadow: 4px 4px 0px $T2;
    color: $white;
    font-size: 18px;
    font-weight: bolder;
    width: 100%;
    margin-top: 1em;
    &:hover {
      box-shadow: none;
      background-color: $S3;
    }
    &:disabled {
      background-color: $G9;
      border-color: $G6;
      box-shadow: none;
      color: $T3;
    }
  }
  section.complete {
    display: none;
    @include size(100vw, 100vh);
    z-index: 9;
    position: fixed;
    top: 0;
    left: 0;
    background-color: rgba(0, 0, 0, 0.5);
    justify-content: center;
    align-items: center;
    div {
      @include size(90%, auto);
      background-color: #fff;
      box-shadow: 15px 15px 0 0 rgba(0, 0, 0, 0.5);
      max-width: 700px;
      padding: 32px 24px;
      img {
        @include size(30%, auto);
        min-width: 150px;
      }
      h3 {
        margin: 32px 0 8px 0;
        font-size: 22px;
        @media screen and (max-width: 576px) {
          font-size: 16px;
        }
      }
      a {
        @include size(100%);
        display: block;
        background-color: $S1;
        padding: 8px 32px;
        font-size: 18px;
        text-decoration: none;
        color: $white;
        margin-top: 24px;
        border: 1.3px solid rgba(0, 0, 0, 0.87);
        box-shadow: 5px 5px 0 0 rgba(0, 0, 0, 0.5);
        transition: all 0.3s ease;
        &:hover {
          background-color: $S3;
        }
      }
    }
  }
}
</style>

<script>
import 'https://cdnjs.cloudflare.com/ajax/libs/jquery/3.4.1/jquery.min.js'

export default {
  data() {
    return {
      user: {
        postFlag: 'InsertData',
        distribution: '3',
        outletSub: '47',
        mediaSub: '888',
        type: 'Event',
        course: '數位繪畫班',
        name: '',
        cellphone: '',
        email: '',
        city: '',
        area: '',
        gift: '實體講座+全方位線上課程',
        sms: '',
        mail: '',
        agreement: true,
        //客製化項目
        remark: '',
        remark2: ''
      },
      verify: {
        nameError: false,
        nameErrorMsg: '請輸入姓名',
        cellphoneError: false,
        cellphoneErrorMsg: '請輸入電話',
        emailError: false,
        emailErrorMsg: '請輸入信箱',
        courseError: false,
        courseErrorMsg: '請選擇課程',
        cityError: false,
        cityErrorMsg: '請選擇居住縣市',
        areaError: false,
        areaErrorMsg: '請選擇居住區域',
        agreementError: false,
        agreementErrorMsg: '請詳細閱讀並同意隱私權使用條款',
        //客製化項目
        remarkError: false,
        remarkErrorMsg: '請選擇時段',
        remark2Error: false,
        remark2ErrorMsg: '請選擇設計程度'
      },
      city: [],
      area: [],
      url: location.href,
      isSubmitted: false
    }
  },
  mounted() {
    let vm = this
    // eslint-disable-next-line no-undef
    $.ajax({
      url: 'https://www.appedu.com.tw/Librarys/_ajax/Address.php',
      type: 'POST',
      dataType: 'json',
      data: { postFlag: 'LoadCity' },
      success: function (res) {
        vm.city = [...res.data]
      }
    })
  },
  methods: {
    getArea() {
      this.user.area = ''
      let vm = this
      // eslint-disable-next-line no-undef
      $.ajax({
        url: 'https://www.appedu.com.tw/Librarys/_ajax/Address.php',
        type: 'POST',
        dataType: 'json',
        data: {
          postFlag: 'LoadArea',
          CityID: this.$refs.city.value
        },
        success: function (res) {
          vm.area = [...res.data]
          vm.checkInput()
        }
      })
    },
    checkInput() {
      //姓名
      if (this.user.name.trim() == '') {
        this.verify.nameError = true
      } else {
        this.verify.nameError = false
      }
      //電話
      if (this.user.cellphone == '') {
        this.verify.cellphoneError = true
        this.verify.cellphoneErrorMsg = '請輸入電話'
      } else {
        let cellphoneRule = /^(09)[0-9]{8}$/
        let phone = this.user.cellphone.trim()
        if (cellphoneRule.test(phone) && phone.length < 11) {
          this.verify.cellphoneError = false
        } else {
          this.verify.cellphoneError = true
          this.verify.cellphoneErrorMsg = '請輸入正確格式'
        }
      }
      //email
      if (this.user.email == '') {
        this.verify.emailErrorMsg = '請輸入信箱'
        this.verify.emailError = true
      } else {
        // eslint-disable-next-line no-useless-escape
        let emailRule = /^\w+((-\w+)|(\.\w+))*\@[A-Za-z0-9]+((\.|-)[A-Za-z0-9]+)*\.[A-Za-z]+$/
        if (this.user.email.search(emailRule) != -1) {
          this.verify.emailError = false
        } else {
          this.verify.emailError = true
          this.verify.emailErrorMsg = '請輸入正確格式'
        }
      }
      //縣市
      if (this.user.city == '') {
        this.verify.cityError = true
      } else {
        this.verify.cityError = false
      }
      //區域
      if (this.user.area == '') {
        this.verify.areaError = true
      } else {
        this.verify.areaError = false
      }
      //課程
      if (this.user.course == '') {
        this.verify.courseError = true
      } else {
        this.verify.courseError = false
      }
      //使用條款
      if (!this.user.agreement) {
        this.verify.agreementError = true
      } else {
        this.verify.agreementError = false
      }
      //備註項目
      if (this.user.remark == '') {
        this.verify.remarkError = true
      } else {
        this.verify.remarkError = false
      }
      if (this.user.remark2 == '') {
        this.verify.remark2Error = true
      } else {
        this.verify.remark2Error = false
      }
    },
    sendForm() {
      let vm = this
      this.isSubmitted = true
      this.checkInput()
      //send
      if (
        !this.verify.nameError &&
        !this.verify.cellphoneError &&
        !this.verify.emailError &&
        !this.verify.cityError &&
        !this.verify.areaError &&
        !this.verify.courseError &&
        !this.verify.agreementError &&
        //客製化項目
        !this.verify.remarkError &&
        !this.verify.remark2Error
      ) {
        // eslint-disable-next-line no-undef
        $.ajax({
          url: 'https://www.appedu.com.tw/Librarys/_ajax/Distribution.php',
          type: 'POST',
          dataType: 'json',
          data: {
            postFlag: this.user.postFlag,
            distribution_id: this.user.distribution,
            outlet_sub_id: this.user.outletSub,
            media_sub_id: this.user.mediaSub,
            type: this.user.type,
            course: this.user.course,
            name: this.user.name,
            cellphone: this.user.cellphone,
            email: this.user.email,
            zip_id: this.user.area,
            remark: `頁面網址：${this.url}\n我對設計了解的程度：${this.user.remark2} ， 方便聯繫時段：${this.user.remark}`,
            gift: this.user.gift,
            sms_id: this.user.sms ?? 0,
            mail_id: this.user.mail ?? 0
          },
          success: function () {
            // alert('資料已送出，將安排專人與您聯絡')
            // window.location.assign('https://www.appedu.com.tw/')
            // vm.$refs.formComplete.style.display = 'flex'

            sessionStorage.setItem(
              'uinfo',
              JSON.stringify({
                name: vm.user.name,
                cellphone: vm.user.cellphone,
                email: vm.user.email
              })
            )
            window.open('./../appedu/thank-you-page/')
            vm.resetFrom()
            sessionStorage.removeItem('uinfo')
          }
        })
      }
    },
    resetFrom() {
      this.user.name = ''
      this.user.cellphone = ''
      this.user.email = ''
      this.user.remark = ''
      this.user.city = ''
      this.user.area = ''
      this.user.remark2 = ''
      this.isSubmitted = false
    }
  }
}
</script>

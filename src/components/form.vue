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
          placeholder="請填入您的真實姓名"
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
          placeholder="請填入您的聯絡電話"
          inputmode="tel"
          @input="checkInput()"
          :class="{ correct: !verify.cellphoneError }"
          required
        />
        <span v-if="verify.cellphoneError && isSubmitted">{{ verify.cellphoneErrorMsg }}</span>
      </label>
      <label for="email" :class="{ error: verify.emailError && isSubmitted }" class="w-100">
        <input
          type="email"
          id="email"
          v-model="user.email"
          placeholder="請填入您的E-mail"
          inputmode="email"
          @input="checkInput()"
          :class="{ correct: !verify.emailError }"
          required
        />
        <span v-if="verify.emailError && isSubmitted">{{ verify.emailErrorMsg }}</span>
      </label>
      <div class="select" :class="{ error: verify.cityError && isSubmitted }">
        <select
          name=""
          ref="city"
          v-model="user.city"
          required
          @change="getArea()"
          :class="{ correct: !verify.cityError && user.city != '' }"
        >
          <option value="" selected hidden>居住縣市</option>
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
          <option value="" selected hidden>居住區域</option>
          <option :value="item.id" v-for="item in area" :key="item.id">{{ item.name }}</option>
        </select>
        <span v-if="verify.areaError && isSubmitted">{{ verify.areaErrorMsg }}</span>
      </div>
      <div class="select w-100" :class="{ error: verify.remarkError && isSubmitted }">
        <select
          name=""
          id=""
          v-model="user.remark"
          @change="checkInput()"
          :class="{ correct: !verify.remarkError && user.remark != '' }"
        >
          <option value="" selected hidden>請選擇學習模式</option>
          <option value="OBO個別指導">OBO個別指導</option>
          <option value="OKBOM線上教學">OKBOM線上教學</option>
          <option value="設計進階課程">設計進階課程</option>
        </select>
        <span v-if="verify.remarkError && isSubmitted">{{ verify.remarkErrorMsg }}</span>
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
      <input class="btn btn-1" type="submit" value="立即送出" @click.prevent="sendForm()" />
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
  border-radius: 8px;
  box-shadow: 0px 4px 32px 0px rgba(0, 0, 0, 0.25);
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
      @media screen and (max-width: 576px) {
        width: 100%;
      }
      input:not([type='checkbox']) {
        width: 100%;
        padding: 12px 16px;
        font-size: 16px;
        background-color: $G11;
        border: none;
        border-radius: 8px;
        color: black;
        @media screen and (max-width: 576px) {
          font-size: 14px;
        }
        &:hover {
          background-color: $G12;
        }
        &::placeholder {
          color: black;
        }
        &:focus {
          outline: 1px solid $G12;
        }
        &:focus-visible {
          outline: 1px solid $G12;
        }
        &.correct {
          background-color: white;
          outline: 1px solid $G12;
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
        }
      }
    }

    .select {
      width: calc(50% - 10px);
      position: relative;
      margin: 1em 0;
      @media screen and (max-width: 576px) {
        width: 100%;
      }
      select {
        width: 100%;
        padding: 12px 16px;
        font-size: 16px;
        appearance: none;
        -moz-appearance: none;
        -webkit-appearance: none;
        background: url(../assets/img/select.svg) no-repeat;
        background-position: calc(100% - 10px) center;
        color: black;
        background-color: $G11;
        border: none;
        border-radius: 8px;
        @media screen and (max-width: 576px) {
          font-size: 14px;
        }
        &:hover {
          background-color: $G12;
        }
        &:focus {
          outline: 1px solid $G12;
        }
        &:focus-visible {
          outline: 1px solid $G12;
        }
        &.correct {
          background-color: white;
          outline: 1px solid $G12;
        }
      }
      span {
        position: absolute;
        bottom: -1.8em;
        left: 0;
        color: $A1;
      }
      &.error {
        select {
          outline: 1px solid $A1;
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
        font-size: 16px;
        margin: 1em auto;
        transition: all 0.3s ease;
        width: auto;
        padding-left: 1.5em;
        cursor: pointer;
        @media screen and (max-width: 576px) {
          font-size: 14px;
        }
        a {
          color: black;
          margin-left: 3px;
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
      input[type='checkbox']:checked + label {
        color: black;
      }
      input[type='checkbox']:checked + label::before {
        box-shadow: 0.1em 0.1em 0 $white inset, -0.1em 0.1em 0 $white inset,
          0.1em -0.1em 0 $white inset, -0.1em -0.1em 0 $white inset, 1em 1em 0 black inset;
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
    background-color: $P1;
    border-radius: 8px;
    color: white;
    width: 100%;
    margin-top: 1em;
    &:hover {
      background-color: $P6;
    }
    &:disabled {
      background-color: $G10;
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
        course: '',
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
        cityError: false,
        cityErrorMsg: '請選擇居住縣市',
        areaError: false,
        areaErrorMsg: '請選擇居住區域',
        agreementError: false,
        agreementErrorMsg: '請詳細閱讀並同意隱私權使用條款',
        //客製化項目
        remarkError: false,
        remarkErrorMsg: '請選擇時段'
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
    this.checkInput()
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
        !this.verify.agreementError &&
        !this.verify.remarkError
      ) {
        // eslint-disable-next-line no-undef
        $.ajax({
          url: '#',
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
            remark: `頁面網址：${this.url}\n我有興趣的學習模式：${this.user.remark}`,
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

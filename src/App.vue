<script>
import navbar from './components/NavBar.vue'
import P1 from './components/Banner.vue'
import P2 from './components/P2.vue'
import P3 from './components/P3.vue'
import P4 from './components/P4.vue'
import P5 from './components/P5.vue'
import P6 from './components/P6.vue'
import P7 from './components/P7.vue'
import P8 from './components/P8.vue'
import P9 from './components/P9.vue'
import P10 from './components/P10.vue'
import P11 from './components/Footer.vue'
import '@/assets/img/share.jpg'

export default {
  components: { P1, P2, P3, P4, P5, P6, P7, P8, P9, P10, P11, navbar }
}
</script>

<template>
  <header>
    <navbar></navbar>
    <P1></P1>
  </header>
  <main>
    <P2></P2>
    <P3></P3>
    <P4></P4>
    <P5></P5>
    <P6></P6>
    <P7></P7>
    <P8></P8>
    <P9></P9>
    <P10></P10>
  </main>
  <footer>
    <P11></P11>
  </footer>
  <a class="receive" href="#form"></a>
</template>

<style lang="scss">
header {
  position: relative;
}

.receive {
  display: none;
  background-image: url('./assets/img/receive.svg?v=1');
  background-size: contain;
  background-repeat: no-repeat;
  background-position: center;
  @include size(132px, 96px);
  position: fixed;
  right: 80px;
  bottom: 100px;
  transition: all 0.5s ease;
  z-index: 9;
  @media screen and (max-width: 996px) {
    @include size(100px, 73px);
    right: 20px;
    bottom: 68px;
  }
  @media screen and (max-width: 576px) {
    @include size(60px, 58px);
    right: 10px;
    bottom: 60px;
  }
  &::after {
    content: '立即領取\A免費課程';
    transition: all 0.3s ease;
    white-space: pre;
    position: absolute;
    bottom: calc(-2.4em - 12px);
    left: calc(50% - 2em);
    font-weight: bolder;
    color: $T1;
    font-size: 18px;
    line-height: 1.2em;
    text-shadow: 1px 1px 0px $white, -1px -1px 0px $white, 1px -1px 0px $white, -1px 1px 0px $white;
    @media screen and (max-width: 768px) {
      bottom: -45px;
      font-size: 18px;
    }
    @media screen and (max-width: 576px) {
      bottom: -35px;
      font-size: 14px;
    }
  }
  &:hover {
    background-image: url('./assets/img/receive_hover.svg?v=1');
    &::after {
      color: $S1;
    }
  }
}

@keyframes scrollTop {
  0% {
    transform: scale(-1) translateY(0px);
  }
  100% {
    transform: scale(-1) translateY(750px);
  }
}
@keyframes scrollBottom {
  0% {
    transform: translateY(-750px);
  }
  100% {
    transform: translateY(0px);
  }
}
</style>

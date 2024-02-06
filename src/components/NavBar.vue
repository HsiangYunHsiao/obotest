<template>
  <nav @mouseleave="openMenu = false">
    <a class="logo" href="https://www.appedu.com.tw/" target="_blank"></a>
  </nav>
</template>

<style lang="scss">
nav {
  position: fixed;
  top: 0;
  left: 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  height: 70px;
  z-index: 9;
  background-color: $transparent;
  @media screen and (max-width: 576px) {
    background-color: #fff;
  }
  a {
    display: flex;
    align-items: center;
    justify-content: center;
    text-decoration: none;
    &.logo {
      margin-left: 60px;
      display: block;
      width: 190px;
      height: 42px;
      background: url(../assets/img/normal_logo.svg) no-repeat top 5px left 12px;
      background-size: 76%;
      &:hover {
        background-image: url(../assets/img/hover_logo.svg);
      }
      @media screen and (max-width: 996px) {
        margin-left: 8px;
      }
      @media screen and (max-width: 768px) {
        margin-left: 0px;
      }
    }
  }
}
</style>

<script></script>

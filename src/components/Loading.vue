<template>
  <div class="loading">
    <div class="container">
      <div class="circle"></div>
      <div class="circle"></div>
      <div class="circle"></div>
      <div class="circle"></div>
      <div class="circle"></div>
    </div>
  </div>
</template>

<script lang="ts">
export default {
  name: 'Loading',
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.loading {
  position: relative;
  width: 100%;
  height: calc(100vh - 57px);
  background-color: rgb(230, 252, 245);
  .container {
    height: 100%;
    width: 80%;
    margin: 0 10%;
    display: flex;
    align-items: center;
    filter: contrast(30); //父元素设置contrast
    background-color: #fff9db;
    justify-content: space-between;
    .circle {
      height: 100px;
      width: 120px;
      background: #1aa7ff;
      border-radius: 50%;
      position: absolute;
      left: 25%;
      filter: blur(20px); //子元素设置blur
      transform: scale(0.1);
      transform-origin: left top;
      animation: move 4s cubic-bezier(0.44, 0.79, 0.83, 0.96) infinite;
      &:nth-child(2) {
        animation-delay: 0.4s;
      }
      &:nth-child(3) {
        animation-delay: 0.8s;
      }
      &:nth-child(4) {
        animation-delay: 1.2s;
      }
      &:nth-child(5) {
        animation-delay: 1.6s;
      }
    }
    @keyframes move {
      //子元素的位移和尺寸动画
      0% {
        transform: translateX(10px) scale(0.3);
      }
      45% {
        transform: translateX(270px) scale(0.8);
      }
      85% {
        transform: translateX(540px) scale(0.1);
      }
    }
  }
}
</style>

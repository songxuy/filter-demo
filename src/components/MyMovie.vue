<template>
  <div class="movie">
    <div class="container">
      <div class="pic"></div>
      <div class="text">
        <p>如果生活中有什么使你感到快乐，那就去做吧</p>
        <br />
        <p>不要管别人说什么</p>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
export default {
  name: 'MyMovie',
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.movie {
  position: relative;
  width: 100%;
  height: calc(100vh - 57px);
}
.container {
  position: relative;
  width: 100%;
  height: 100%;
  .pic {
    height: 100%;
    width: 100%;
    position: absolute;
    background: url('../assets/saye.jpg') no-repeat;
    background-size: cover;
    animation: fade-away 2.5s linear forwards;
  }
  .text {
    position: absolute;
    line-height: 55px;
    color: #fff;
    font-size: 36px;
    text-align: center;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    opacity: 0;
    animation: show 2s cubic-bezier(0.74, -0.1, 0.86, 0.83) forwards;
  }
  @keyframes fade-away {
    //背景图的明暗度动画
    30% {
      filter: brightness(1);
    }
    100% {
      filter: brightness(0);
    }
  }
  @keyframes show {
    //文字的透明度动画
    20% {
      opacity: 0;
    }
    100% {
      opacity: 1;
    }
  }
}
</style>

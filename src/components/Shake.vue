<template>
  <div class="shake">
    <p class="shaky">Such a joyful night!</p>
  </div>
  <svg width="0" height="0">
    <filter id="displacement-text-filter">
      <!--定义feTurbulence滤镜-->
      <feTurbulence baseFrequency="0.02" seed="0">
        <!--这是svg动画的定义方式，通过动画不断改变seed的值，形成抖动效果-->
        <animate
          attributeName="seed"
          dur="1s"
          keyTimes="0;0.5;1"
          values="1;2;3"
          repeatCount="indefinite"
        ></animate>
      </feTurbulence>
      <feDisplacementMap in="SourceGraphic" scale="10" />
    </filter>
  </svg>
</template>

<script lang="ts">
export default {
  name: 'Shake',
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.shake {
  position: relative;
  width: 100%;
  height: calc(100vh - 57px);
  background-color: rgb(230, 252, 245);
  .shaky {
    font-size: 60px;
    filter: url(#displacement-text-filter);
    text-align: center;
    padding: 20px 0;
  }
}
</style>

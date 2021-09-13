<template>
  <div class="reflect_main">
    <img src="@/assets/moon.png" />
    <img src="@/assets/moon.png" class="reflect" />
    <!--定义svg滤镜，这里使用的是feTurbulence滤镜-->
    <svg width="0" height="0">
      <filter id="displacement-wave-filter">
        <!--baseFrequency设置0.01 0.09两个值，代表x轴和y轴的噪声频率-->
        <feTurbulence baseFrequency="0.01 0.09">
          <!--这是svg动画的定义方式，通过动画不断改变baseFrequency的值，从而形成波动效果-->
          <animate
            attributeName="baseFrequency"
            dur="20s"
            keyTimes="0;0.5;1"
            values="0.01 0.09;0.02 0.13;0.01 0.09"
            repeatCount="indefinite"
          ></animate>
        </feTurbulence>
        <feDisplacementMap in="SourceGraphic" scale="10" />
      </filter>
    </svg>
  </div>
</template>

<script lang="ts">
export default {
  name: 'Reflect',
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.reflect_main {
  position: relative;
  width: 100%;
  height: calc(100vh - 57px);
  background-color: rgb(230, 252, 245);
  display: flex;
  clip-path: inset(10px);
  flex-direction: column;
  img {
    height: 50%;
    width: 100%;
  }
  .reflect {
    transform: translateY(-2px) scaleY(-1);
    //对模拟倒影的元素应用svg filter
    //url中对应的是上面svg filter的id
    filter: url(#displacement-wave-filter);
  }
}
</style>

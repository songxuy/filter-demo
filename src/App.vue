<template>
  <div id="app">
    <div id="nav">
      <p :class="tab === 0 ? 'active' : ''" @click="changeTab(0)">Demo1</p>
      <p :class="tab === 1 ? 'active' : ''" @click="changeTab(1)">Demo2</p>
      <p :class="tab === 2 ? 'active' : ''" @click="changeTab(2)">Demo3</p>
      <p :class="tab === 3 ? 'active' : ''" @click="changeTab(3)">Demo4</p>
    </div>
    <component :is="arr[tab]"></component>
  </div>
</template>
<script lang="ts">
import { defineComponent, ref } from 'vue';
import MyMovie from '@/components/MyMovie.vue';
import MyCard from '@/components/MyCard.vue';
import Grey from '@/components/Grey.vue';
import MyPhoto from '@/components/MyPhtot.vue'
export default defineComponent({
  name: 'App',
  components: {
    MyMovie,
    MyCard,
    Grey,
    MyPhoto,
  },
  setup() {
    let tab = ref(0);
    let arr: Array<string> = ['MyMovie', 'MyCard', 'Grey', 'MyPhoto'];
    const changeTab = (i: number) => {
      tab.value = i;
      if (i === 2) {
        document.body.style.setProperty('filter', 'grayscale(100%)');
      } else {
        document.body.style.removeProperty('filter');
      }
    };
    return {
      tab,
      changeTab,
      arr,
    };
  },
});
</script>
<style lang="scss">
* {
  padding: 0;
  margin: 0;
}
#app {
  position: relative;
  min-width: 100vw;
  min-height: 100vh;
  background-color: #617c8a;
}
#nav {
  position: relative;
  padding: 10px 20px;
  display: flex;
  align-items: center;
  p {
    position: relative;
    padding: 8px 20px;
    font-size: 16px;
    color: #1e80ff;
    background-color: #e8f3ff;
    border-radius: 3px;
    cursor: pointer;
    &.active {
      background-color: #1e80ff;
      color: #fff;
    }
    &:not(:last-child) {
      margin-right: 20px;
    }
  }
}
</style>

<template>
  <div class="photo">
    <p class="title">Some Wallpapers</p>
    <div class="pic_container">

    </div>
  </div>
</template>

<script lang="ts">
export default {
  name: 'MyPhoto',
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.photo {
  position: relative;
  width: 100%;
  height: calc(100vh - 57px);
  background-color: #EEEDDB;
  .title {
    position: relative;
    font-size: 30px;
    color: #6C5D4B;
    padding: 30px 80px;
    font-weight: bold;
  }
  .pic_container {
    position: relative;
    margin: 0 80px;
    height: calc(100% - 100px);
  }
}
</style>

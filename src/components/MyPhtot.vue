<template>
  <div class="photo">
    <p class="title">Some Wallpapers</p>
    <div class="pic_container">
      <img src="@/assets/1.jpg" class="pic img1" />
      <img src="@/assets/2.jpg" class="pic img2" />
      <img src="@/assets/3.jpg" class="pic img3" />
      <img src="@/assets/4.jpeg" class="pic img4" />
      <img src="@/assets/5.jpg" class="pic img5" />
      <img src="@/assets/6.jpg" class="pic img6" />
      <img src="@/assets/7.jpg" class="pic img7" />
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
  background-color: #eeeddb;
  .title {
    position: relative;
    font-size: 30px;
    color: #6c5d4b;
    padding: 30px 80px;
    font-weight: bold;
  }
  .pic_container {
    position: relative;
    margin: 0 80px;
    height: calc(100% - 100px);
    .pic {
      position: absolute;
      border: 3px solid #fff;
      box-shadow: 0 10px 50px #5f2f1182;
      filter: sepia(30%) saturate(40%) hue-rotate(5deg);
      transition: transform 1s;
      cursor: pointer;
    }
    .pic:hover {
      filter: none;
      transform: scale(1.2) translateX(10px);
      z-index: 1;
    }
    .img1 {
      width: 250px;
      height: 180px;
      top: 40%;
    }
    .img2 {
      width: 250px;
      height: 180px;
      top: 25%;
      left: 200px;
    }
    .img3 {
      width: 280px;
      height: 180px;
      top: 20%;
      left: 500px;
    }
    .img4 {
      width: 250px;
      height: 150px;
      top: 40%;
      left: 700px;
    }
    .img5 {
      width: 250px;
      height: 150px;
      top: 30%;
      left: 900px;
    }
    .img6 {
      width: 300px;
      height: 200px;
      top: 10%;
      left: 1100px;
    }
    .img7 {
      width: 300px;
      height: 200px;
      top: 22%;
      left: 1400px;
    }
  }
}
</style>

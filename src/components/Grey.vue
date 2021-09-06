<template>
  <div class="my-card">
    <ul class="cards">
      <li class="card">
        <p class="title">Flower</p>
        <p class="content">The flowers mingle to form a blaze of color.</p>
      </li>
      <li class="card">
        <p class="title">Sunset</p>
        <p class="content">The sunset glow tinted the sky red.</p>
      </li>
      <li class="card">
        <p class="title">Plain</p>
        <p class="content">
          The winds came from the north, across the plains, funnelling down the valley.
        </p>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
export default {
  name: 'Grey',
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.my-card {
  position: relative;
  width: 100%;
  height: calc(100vh - 77px);
  padding-top: 20px;
}
.cards {
  position: relative;
  display: flex;
  margin: 0 150px;
  align-items: center;
  justify-content: space-between;
  .card {
    width: 350px;
    height: 550px;
    padding: 40px 20px;
    position: relative;
    border-radius: 10px;
    list-style: none;
    cursor: pointer;
    .title {
      position: relative;
      font-size: 26px;
      color: #000;
      z-index: 2;
    }
    .content {
      position: relative;
      font-size: 18px;
      color: #000;
      margin-top: 20px;
      z-index: 2;
    }
    &::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      bottom: 0;
      right: 0;
      width: 3 90px;
      height: 630px;
      border-radius: 20px;
      filter: blur(0px) opacity(1);
      transition: filter 200ms linear, transform 200ms linear;
    }
    &:nth-child(1)::before {
      background: url('../assets/head9.jpg');
      background-size: cover;
    }
    &:nth-child(2)::before {
      background: url('../assets/head12.jpg');
      background-size: cover;
    }
    &:nth-child(3)::before {
      background: url('../assets/head13.jpg');
      background-size: cover;
    }
    &:hover::before {
      filter: saturate(1.2);
      transform: scale(1.05);
    }
  }
  &:hover {
    & > .card:not(:hover)::before {
      filter: blur(5px) opacity(0.8) brightness(0.8);
    }
  }
}
</style>

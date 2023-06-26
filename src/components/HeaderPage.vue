<template>
  <header class="main-header">
    <div class="layers">
      <div class="layers-header">
        <div class="layers-caption">Welcome to Parallax</div>
        <div class="layers-title">Fairy Forest</div>
      </div>
      <div class="layer layers-base base"></div>
      <div class="layer layers-middle middle"></div>
      <div class="layer layers-front front"></div>
    </div>
  </header>
</template>

<script setup>

</script>

<style scoped>

.main-header {
  position: relative;
}

.main-header::after {
  content: "";
  position: absolute;
  z-index: 100;
  width: 100%;
  height: calc(var(--index) * 10);
  background-image: url("../../img/ground.png");
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
  bottom: calc(var(--index) * -4.5);
}

.layers {
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  overflow: hidden;
  position: relative;
}

.layer {
  position: absolute;
  width: 100%;
  height: 100%;
  background-size: cover;
  background-position: center;
  will-change: transform;
  z-index: 2;
  transition: var(--transition);
}

.layers-base {
  transform: translate3d(0, calc(var(--scrollTop) / 1.6), 0);
  z-index: 0;
}

.layers-middle {
  transform: translate3d(0, calc(var(--scrollTop) / 2.5), 0);
}

.layers-front {
  transform: translate3d(0, calc(var(--scrollTop) / 5.7), 0);
}

.base {
  background-image: url(../../img/layer-base.png);
}

.middle {
  background-image: url(../../img/layer-middle.png);
}

.front {
  background-image: url(../../img/layer-front.png);
}

.layers-header {
  z-index: 1;
  transform: translate3d(0, calc(var(--scrollTop) / 2), 0);
  transition: var(--transition);
  will-change: transform;
  text-transform: uppercase;
  font-weight: 900;
  color: var(--text);
  text-shadow: 0 0 15px #9d822b;
}

.layers-title {
  font-size: calc(var(--index) * 2.65);
  letter-spacing: calc(var(--index) / 2.25);
}

.layers-caption {
  font-size: calc(var(--index) / 1.175);
  letter-spacing: calc(var(--index) / 3.5);
  margin-top: calc(var(--index) * -.75);
}

</style>
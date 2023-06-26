<template>
  <article class="main-article dungeon">
    <div class="main-article_content">
      <h2 class="main-article_header">parallax</h2>
      <p class="main-article_paragraph">Parallax is a displacement
        or difference in the apparent position of an object
        viewed along two different lines of sight and is measured by the angle
        or half-angle of inclination between those two lines.</p>
    </div>
  </article>
</template>

<script setup>

</script>

<style scoped>

.dungeon {
  background-image: url(../../img/dungeon.jpg);
}

.main-article {
  --main-article-transform: translate3d(0, calc(var(--scrollTop) / -7.5), 0);
  min-height: 100vh;
  background-size: cover;
  background-position: center;
  color: var(--text);
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
  text-align: center;
  top: -1px;
  z-index: 10;
}

.main-article_header {
  text-transform: uppercase;
  font-size: calc(var(--index) * 1.8);
  letter-spacing: calc(var(--index) / 7.5);
  transform: var(--main-article-transform);
  transition: var(--transition);
  will-change: transform;
}

.main-article_paragraph {
  max-width: calc(var(--index) * 30);
  font-size: calc(var(--index) * .9);
  margin-top: calc(var(--index) / 1.25);
  transform: var(--main-article-transform);
  transition: var(--transition);
  will-change: transform;
}

</style>
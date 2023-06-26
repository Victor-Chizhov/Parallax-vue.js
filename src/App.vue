<template>
  <div class="wrapper">
    <div class="content">
      <HeaderPage />
      <FooterPage />
    </div>
  </div>
</template>

<script setup>
import FooterPage from "@/components/FooterPage.vue";
import HeaderPage from "@/components/HeaderPage.vue";

gsap.registerPlugin(ScrollTrigger, ScrollSmoother)
ScrollSmoother.create({
  wrapper: '.wrapper',
  content: '.content'
})
window.addEventListener('scroll', function (ev) {
  document.documentElement.style.setProperty('--scrollTop', `${this.scrollY}px`) // Update method
})

</script>

<style scoped>
.content {
  will-change: transform;
}

</style>

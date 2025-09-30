<template>
  <section class="soil-section">
    <svg id="seed" width="50" height="50" viewBox="0 0 100 100">
      <circle cx="50" cy="50" r="10" fill="#6b4226" />
    </svg>
  </section>
</template>

<script setup>
import { onMounted } from 'vue';
import { gsap } from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';

gsap.registerPlugin(ScrollTrigger);

onMounted(() => {
  gsap.fromTo(
    '#seed',
    { y: -200, opacity: 0 },
    {
      y: 0,
      opacity: 1,
      scrollTrigger: {
        trigger: '.soil-section',
        start: 'top 80%',   // when top of section hits 80% of viewport
        end: 'bottom top',  // end at bottom of section
        scrub: true,        // ties animation to scroll
      },
    }
  );
});
</script>

<style scoped>
.soil-section {
  height: 100vh;
  background-color: #a17f5a; /* placeholder soil color */
  display: flex;
  justify-content: center;
  align-items: flex-start;
  padding-top: 50px;
}
</style>

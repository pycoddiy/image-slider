<template>
    <div class="carousel">
      <div class="carousel-inner">
        <CarouselItem v-for="(slide, index) in slides" :slide="slide" :key="`item-${index}`" :current-slide="currentSlide" :index="index" />
        <P>{{ currentSlide }}</P>
      </div>
    </div>
</template>

<script setup>
  import { useInterval } from '@vueuse/core'
  const { slides } = defineProps(['slides']);

  let currentSlide = 1;

  const nextSlide = (count) => {
    currentSlide = (currentSlide + 1) % slides.length;
    console.log(currentSlide);
  };

  useInterval(5000, {callback: nextSlide})  
</script>

<style scoped>
  .carousel {
    display: flex;
    justify-content: center;
  }

  .carousel-inner {
    position: relative;
    width: 900px;
    height: 400px;
    overflow: hidden;
  }
</style>
<template>
  <div class="carousel">
    <div class="carousel-inner">
      <CarouselItem v-for="(slide, index) in slides" :slide="slide" :key="`item-${index}`" :current-slide="currentSlide" :index="index" />
    </div>
  </div>
</template>

<script setup>
  import { useInterval } from '@vueuse/core'
  import { ref } from 'vue'

  const { slides } = defineProps(['slides']);

  const currentSlide = ref(0);

  const nextSlide = (count) => {
    currentSlide.value = (currentSlide.value + 1) % slides.length;
    console.log(currentSlide.value);
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
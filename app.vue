<template>
  <div class="m-10">
    <Carousel :slides="slides" />
  </div>
</template>

<script>
export default {
  name: 'App',
  data: () => ({
    slides: [
      "https://picsum.photos/id/1032/900/400",
      "https://picsum.photos/id/1033/900/400",
      "https://picsum.photos/id/1037/900/400",
      "https://picsum.photos/id/1035/900/400",
      "https://picsum.photos/id/1036/900/400",
    ],
  }),
}
</script>

<style scoped>
</style>
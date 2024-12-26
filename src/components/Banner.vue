<template>
  <div class="relative bg-cover bg-center h-96" :style="{ backgroundImage: `url(${video.thumbnail})` }">
    <div class="absolute inset-0 bg-gradient-to-t from-gray-900 via-transparent"></div>
    <div class="absolute bottom-10 left-8 space-y-4">
      <h1 class="text-4xl font-bold text-white">{{ video.title }}</h1>
      <p class="text-gray-300 max-w-md">{{ video.description }}</p>
      <button @click="playVideo" class="bg-blue-600 hover:bg-blue-500 text-white py-2 px-6 rounded-lg">
        Reproducir
      </button>

    </div>
  </div>
</template>

<script>
export default {
  props: ["video"],
  methods: {
    playVideo() {
      this.$emit("play-video", this.video); // Emite el evento con el video
    },
  },
};
</script>

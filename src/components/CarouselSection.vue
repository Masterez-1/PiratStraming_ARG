<template>
  <section class="mb-8">
    <h2 class="text-lg md:text-xl font-semibold mb-4">{{ title }}</h2>
    <div class="flex overflow-x-auto space-x-4 scrollbar-hide">
      <div v-for="video in videos" :key="video.id"
        class="bg-gray-800 w-36 sm:w-44 md:w-48 lg:w-64 flex-shrink-0 rounded-lg shadow hover:shadow-lg transition cursor-pointer"
        @click="$emit('play', video)">
        <img :src="video.thumbnail" :alt="video.title" class="w-full h-48 sm:h-56 md:h-64 object-cover rounded-t-lg" />
        <h3 class="p-4 text-xs sm:text-sm md:text-base font-medium">{{ video.title }}</h3>
      </div>
    </div>
  </section>
</template>


<script>
export default {
  props: ["title", "videos"],
};
</script>
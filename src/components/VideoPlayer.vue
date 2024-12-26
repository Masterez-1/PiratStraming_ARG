<template>
  <div v-if="isOpen"
    class="fixed inset-0 bg-black bg-opacity-75 flex justify-center items-center z-50">
    <div class="relative bg-gray-800 rounded-xl p-6 w-full max-w-4xl shadow-lg">
      <button
        class="absolute top-4 right-4 text-white"
        @click="close" aria-label="Cerrar reproductor">
        ✖
      </button>
      <h2 class="text-2xl font-semibold text-white mb-6 text-center">{{ video.title }}</h2>
      <video controls autoplay class="w-full h-auto rounded-lg shadow-md" :src="video.src"></video>
      <p class="mt-6 text-gray-300 text-center text-sm">{{ video.description }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ["isOpen", "video"],
  methods: {
    close() {
      this.$emit("close");  // Emitir el evento para cerrar el modal
    },
  },
};
</script>


<style scoped>
body.modal-open {
  overflow: hidden;
}

div[role="dialog"] {
  animation: fadeIn 0.3s ease-out;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: scale(0.95);
  }

  to {
    opacity: 1;
    transform: scale(1);
  }
}
</style>

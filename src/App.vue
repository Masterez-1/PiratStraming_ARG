<template>
  <div id="app" class="bg-gray-900 text-white min-h-screen">
    <Header />
    <Banner :video="featuredVideo" />
    <main class="mt-8">
      <CarouselSection
        :title="'Películas'"
        :videos="movies"
        @play="playVideo"
      />
      <CarouselSection
        :title="'Series'"
        :videos="series"
        @play="playVideo"
      />
      <CarouselSection
        :title="'Documentales'"
        :videos="documentaries"
        @play="playVideo"
      />
    </main>
    <Footer />
    <VideoPlayer
      v-if="isModalOpen"
      :isOpen="isModalOpen"
      :video="activeVideo"
      @close="isModalOpen = false"
    />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Banner from "./components/Banner.vue";
import CarouselSection from "./components/CarouselSection.vue";
import Footer from "./components/Footer.vue";
import VideoPlayer from "./components/VideoPlayer.vue";
import { movies, series, documentaries, featuredVideo } from "./data/videos";

export default {
  components: { Header, Banner, CarouselSection, Footer, VideoPlayer },
  data() {
    return {
      movies,
      series,
      documentaries,
      featuredVideo,
      isModalOpen: false,
      activeVideo: null,
    };
  },
  methods: {
    playVideo(video) {
      this.activeVideo = video;
      this.isModalOpen = true;
    },
  },
};
</script>

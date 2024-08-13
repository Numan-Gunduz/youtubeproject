<template>
  <div>
    <ul class="videoList">
      <VideoListItem
        @videoSelect="onVideoSelect"
        v-for="video in videos"
        :key="video.etag"
        :video="video"
      />
    </ul>
  </div>
</template>

<script>
import VideoListItem from "./VideoListItem.vue";
export default {
  props: ["videos"],
  emits: ["videoSelect"],
  components: {
    VideoListItem,
  },
  methods: {
    onVideoSelect(video) {
      this.$emit("videoSelect", video);
    },
  },
};
</script>

<style scoped>
.videoList {
  list-style-type: none;
  width: 100%;
}
</style>

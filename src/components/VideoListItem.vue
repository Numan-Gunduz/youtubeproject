<template>
  <div>
    <li class="videoListItem" @click="onVideoSelect">
      <img class="videoImg" :src="imageUrl" />
      <div>
        {{ video.snippet.title }}
      </div>
    </li>
  </div>
</template>

<script>
export default {
  props: ["video"],
  emits: ["videoSelect"],
  computed: {
    imageUrl() {
      return this.video.snippet.thumbnails.medium.url;
    },
  },
  methods: {
    onVideoSelect() {
      this.$emit("videoSelect", this.video);
    },
  },
};
</script>

<style scoped>
.videoListItem {
  display: flex;
  border: 1px solid green;
  border-radius: 30px;
  margin: 20px;
  box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
  align-items: center;
  /* text-align: center; */
}
.videoImg {
  border-radius: 30px 0px 0px 30px;
  margin-right: 30px;
}
</style>

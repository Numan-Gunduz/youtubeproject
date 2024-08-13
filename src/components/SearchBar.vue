<template>
  <div>
    <form class="searchform" @submit.prevent="handleSubmit">
      <input class="searchInput" v-model="searchTerm" type="text" />
      <button class="searchButton">Ara</button>
    </form>
  </div>
</template>

<script>
export default {
  emits: ["termChange"],
  data() {
    return {
      searchTerm: "",
    };
  },
  methods: {
    handleSubmit() {
      this.$emit("termChange", this.searchTerm);
      this.searchTerm = "";
    },
  },
};
</script>

<style scoped>
.searchform {
  display: flex;
  margin: 25px 0px;
}
.searchInput {
  width: 85%;
  padding: 8px;
  margin-right: 20px;
  border-radius: 20px;
}
.searchButton {
  width: 15%;
  border: none;
  background-color: green;
  color: white;
  font-size: 18px;
  border-radius: 20px;
  cursor: pointer;
}
</style>

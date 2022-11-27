<template>
  <nav class="d-flex justify-content-center align-items-center bg-black" style="height: 60px;">
      <!-- <div class="w-70 bg-dark pl-26 border border-0"> -->
        <InputSearch v-model="searchText" />

  </nav>
</template>
<script>
import InputSearch from "@/components/InputSearch.vue";
export default {
  components: {
    InputSearch,
  },
  data() {
    return {
      activeIndex: -1,
      searchText: "",
    };
  },
  watch: {
    searchText() {
      this.activeIndex = -1;
    },
  },
};
</script>
<style scoped>
.page {
  text-align: left;
  max-width: 750px;
}
</style>
<script>
export default {
  props: {
    modelValue: { type: String, default: "" },
  },
  emits: ["submit", "update:modelValue"],
  methods: {
    updateModelValue(e) {
      this.$emit("update:modelValue", e.target.value);
    },
    submit() {
      this.$emit("submit");
      
    },
  },
};
</script>
<template>
  <div>
    <input
      type="text"
      class="search_box"
      placeholder="Search for movie......"
      :value="modelValue"
      @input="updateModelValue"
      @keyup.enter="submit"
    />
  </div>
</template>
<style scoped>
.search_box {
  width: clamp(200px,70vw,660px);
  height: 36px;
  background-color: #070707;
  border: 0px;
  border-bottom: 1px solid #8f8f8f;
  padding-left: 26px;
  color: #fff;
}

input::placeholder{
  font-family: Montserrat;
  font-size: 14px;
  color: #fff;
}

textarea:focus, input:focus{
  outline: none;
}
</style>

<template>
  <div class="rating">
    <div
      class="rating-star"
      v-for="index in 5"
      :key="index"
      @click="handleClick(index)"
    >
      <img src="../img/star.png" alt="Rating Star" v-if="index <= modelValue" />
      <img
        src="../img/unstar.png"
        alt="Rating Star"
        v-if="index > modelValue"
      />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    modelValue: {
      type: Number,
      default: 0,
    },
  },
  emits: ["update:modelValue"],
  methods: {
    handleClick(index) {
      this.$emit("update:modelValue", index);
    },
  },
  data() {
    return {};
  },
};
</script>

<style scoped>
.rating {
  width: 200px;
  display: flex;
  align-items: center;
}
.rating-star {
  margin: 2px;
  cursor: pointer;
}
.rating-star img {
  height: 40px;
}
.rating-star img:hover {
  transform: scale(1.1);
}
</style>

<template>
  <div class="the-card">
    <div class="the-card__title">{{ demo_title }}</div>
    <div class="the-card__body"><slot name="body"></slot></div>
    <div class="the-card__footer" v-if="$slots.footer">
      <slot name="footer"></slot>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    demo_title: {
      type: String,
    },
  },
  data() {
    return {};
  },
};
</script>

<style scoped>
.the-card {
  width: 300px;
  min-height: 200px;
  border: 1px solid black;
  margin: 20px auto;
}
.the-card__title {
  background: rgb(2, 96, 2);
  padding: 5px 11px;
  color: #fff;
}
.the-card__body {
  padding: 11px;
}

.the-card__footer {
  background: rgba(192, 191, 191, 0.485);
  text-align: center;
  padding: 10px 10px;
  font-weight: bold;
  color: crimson;
}
</style>

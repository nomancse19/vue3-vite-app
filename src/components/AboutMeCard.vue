<template>
  <div>
    <div class="main">
      <h3>About Me Card</h3>
    </div>
    <div class="the-content">
      <div class="content-title">{{ about_title }}</div>
      <div class="content-body">{{ about_body }}</div>
    </div>
  </div>
</template>

<script>
export default {
  inject: ["about_title", "about_body"],
  data() {
    return {
      hide_button: true,
      show_button: false,
    };
  },
  methods: {
    hideTitle() {
      this.$emit("hide-title", this.about_info);
      // this.$refs.hide_button.color("red");
      this.hide_button = false;
      this.show_button = true;
    },
  },
};
</script>

<style scoped>
.the-content {
  width: 250px;
  border: 1px solid rgb(2, 97, 118);
  margin: 1px auto;
  min-height: 100px;
}
.content-body {
  padding: 10px 10px;
}
.content-title {
  background: rgb(16, 74, 74);
  color: #fff;
  padding: 5px 5px;
}
.main {
  width: 960px;
  margin: 10px auto;
}
</style>

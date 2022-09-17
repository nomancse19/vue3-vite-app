<template>
  <div class="the-comment">
    <textarea
      :value="modelValue"
      @input="handleInput"
      id=""
      cols="40"
      rows="5"
      v-bind="$attrs"
    ></textarea>
    <div class="text-right">
      <button>{{ buttonText }}</button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    modelValue: {
      type: String,
      default: "",
    },
    buttonText: {
      type: String,
      default: "",
    },
  },
  inheritAttrs: false,
  methods: {
    handleInput(e) {
      //console.log(e.target.value);
      this.$emit("update:modelValue", e.target.value);
    },
  },
};
</script>

<style scoped>
.the-comment {
  width: 388px;
  border: 1px solid gray;
  border-radius: 5px;
  color: gray;
  background-color: rgb(255, 254, 247);
  margin-right: 150px;
  padding: 35px;
}
input {
  padding: 7px 9px;
  border-radius: 3px;
  width: 100%;
  border: 1px solid gray;
  margin-bottom: 11px;
}
.row {
  display: flex;
}
.col-6 {
  flex: 1;
  padding: 0 2px;
}
.text-right {
  text-align: right;
}
</style>

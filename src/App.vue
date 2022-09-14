<template>
  <HelloWorld msg="Welcome To My Vue Js Site" class="hello"></HelloWorld>
  <p>My Rating : {{ myRating }}</p>
  <the-rating v-model="myRating"></the-rating>
</template>
<script>
import TheRating from "./components/TheRating.vue";
import HelloWorld from "./components/HelloWorld.vue";
export default {
  name: "App",

  data() {
    return {
      myRating: 3,
    };
  },
  methods: {},
  components: {
    TheRating,
    HelloWorld,
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>

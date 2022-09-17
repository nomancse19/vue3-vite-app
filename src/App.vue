<template>
  <HelloWorld msg="Welcome To My Vue Js Site" class="hello"></HelloWorld>
  <div class="container">
    <the-comment
      v-model="myComment"
      buttonText="Continue"
      class="shadow"
      placeholder="Enter Text Here..."
    ></the-comment>
    <br />
    <br />
    <br />
    <hr />
    <p>Your Comment is : {{ myComment }} <br /></p>
  </div>
</template>
<script>
import HelloWorld from "./components/HelloWorld.vue";
import TheComment from "./components/TheComment.vue";
export default {
  name: "App",

  data() {
    return {
      myComment: "",
    };
  },
  methods: {
    checkClick() {
      alert("Check Click Alert On");
    },
  },
  components: {
    HelloWorld,
    TheComment,
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.container {
  padding: 22px;
}
body {
  line-height: 1.8;
}
button {
  padding: 5px 7px;
}
.shadow {
  box-shadow: 0 0 3px black;
}
</style>

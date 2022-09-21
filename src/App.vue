<template>
  <HelloWorld msg="Welcome To My Vue Js Site" class="hello"></HelloWorld>
  <div class="container">
    <the-comment
      v-model="myComment"
      buttonText="Continue"
      class="shadow"
      placeholder="Enter Text Here..."
      @continueClick="handleContiuneButton()"
    ></the-comment>
    <br />
    <br />
    <br />
    <hr />
    <p>Your Comment is : {{ myComment }} <br /></p>
    <the-dialog heading="Are You Sure To Want Comment" v-if="showDialog">
      <p>this is body of notifications bar ...</p>
    </the-dialog>
  </div>
</template>
<script>
import HelloWorld from "./components/HelloWorld.vue";
import TheComment from "./components/TheComment.vue";
import TheDialog from "./components/TheDialog.vue";
export default {
  name: "App",

  data() {
    return {
      myComment: "",
      showDialog: false,
    };
  },
  methods: {
    checkClick() {
      alert("Check Click Alert On");
    },

    handleContiuneButton() {
      this.showDialog = true;
    },
  },
  components: {
    HelloWorld,
    TheComment,
    TheDialog,
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
  color: red;
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

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

    <button @click="showNotification()">Show Notifications</button>

    <the-dialog heading="Are You Sure To Want Comment" v-if="showDialog">
      <p>this is body of notifications bar ...</p>

      <div class="footer_dialog">
        <button @click="showDialog = false">Ok</button>
        <button @click="showDialog = false">Close</button>
      </div>
    </the-dialog>
    <the-notification
      v-for="(notification_data, i) in notifications"
      :key="i"
      :text="notification_data"
    >
    </the-notification>
  </div>
</template>
<script>
import HelloWorld from "./components/HelloWorld.vue";
import TheComment from "./components/TheComment.vue";
import TheDialog from "./components/TheDialog.vue";
import TheNotification from "./components/TheNotification.vue";
export default {
  name: "App",

  data() {
    return {
      myComment: "",
      showDialog: false,
      notifications: [],
    };
  },
  methods: {
    checkClick() {
      alert("Check Click Alert On");
    },

    handleContiuneButton() {
      this.showDialog = true;
    },
    showNotification() {
      this.notifications.push("You Have A New Notifications");
      setTimeout(() => {
        this.notifications.shift();
      }, 2000);
    },
  },
  components: {
    HelloWorld,
    TheComment,
    TheDialog,
    TheNotification,
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
  margin: 5px;
}
.shadow {
  box-shadow: 0 0 3px black;
}
.footer_dialog {
  bottom: 0;
  margin-top: 10px;
}
</style>

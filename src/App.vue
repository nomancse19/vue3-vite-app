<template>
  <HelloWorld msg="Welcome To My Vue Js Site" class="hello"></HelloWorld>
  <div class="container">
    <Register></Register>
  </div>
</template>
<script>
import HelloWorld from "./components/HelloWorld.vue";
import Login from "./components/Login.vue";
import Register from "./components/Register.vue";
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
    Login,
    Register,
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
  margin: 5px;
}
.shadow {
  box-shadow: 0 0 3px black;
}
.footer_dialog {
  bottom: 0;
  margin-top: 10px;
}
input {
  padding: 5px 11px;
  margin-bottom: 11px;
}
</style>

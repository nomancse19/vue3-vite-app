<template>
  <HelloWorld msg="Welcome To My Vue Js Site" class="hello"></HelloWorld>
  <div class="container">
    <h1>New User Registrations</h1>
    <label for="">Your Name </label><br />
    <input
      type="text"
      placeholder="Enter Your Name"
      v-model="formData.fullName"
    /><br />

    <label for="">About Your Info </label><br />
    <textarea
      placeholder="Enter Something About You ..."
      cols="30"
      rows="2"
      v-model="formData.aboutYou"
    ></textarea
    ><br />
    <label for="">Select Gender</label>
    <label for=""
      ><input
        type="radio"
        name="gender"
        v-model="formData.gender"
        value="Male"
        class="ml-2"
      />Male</label
    >
    <label for=""
      ><input
        type="radio"
        name="gender"
        value="Female"
        class="ml-2"
        v-model="formData.gender"
      />Female</label
    >
    <label for=""
      ><input
        type="radio"
        name="gender"
        value="Others"
        v-model="formData.gender"
        class="ml-2"
      />Other's</label
    >
    <br />
    <label for="">Select Language</label><br />
    <select v-model="formData.language">
      <option value="">Select Any One Language</option>
      <option value="Java">Java</option>
      <option value="PHP">PHP</option>
      <option value="Python">Python</option>
      <option value="ASP-Net">ASP-Net</option>
      <option value="C++">C++</option></select
    ><br />

    <label for="">Select Skills</label><br />
    <select v-model="formData.skills" multiple>
      <option value="Java">Java</option>
      <option value="PHP">PHP</option>
      <option value="Python">Python</option>
      <option value="ASP-Net">ASP-Net</option>
      <option value="C++">C++</option>
    </select>
    <br />
    <label for="">Agreement</label><br />
    <label for=""
      ><input type="checkbox" v-model="formData.agreed" />A agree to the terms
      and conditions</label
    ><br />
    <label for="">Agreement</label><br />
    <label for=""
      ><input
        type="checkbox"
        value="facebook"
        v-model="formData.socialAccount"
      />Facebook</label
    >
    <label for=""
      ><input
        type="checkbox"
        value="twitter"
        v-model="formData.socialAccount"
      />Twitter</label
    >
    <label for=""
      ><input
        type="checkbox"
        value="youtube"
        v-model="formData.socialAccount"
      />Youtube</label
    >
    <label for=""
      ><input
        type="checkbox"
        value="imo"
        v-model="formData.socialAccount"
      />Imo</label
    >
    <br />
    <hr />
    <h4 style="color: blueviolet">Your Given Information</h4>
    <div v-for="(FormValue, key) in formData" :key="key">
      <strong>{{ key }} : {{ FormValue }}</strong>
    </div>
    <!-- <div class="tab"> -->
    <!-- <div class="tab__menu">
        <div
          class="tab__menu-item"
          v-for="(tab, i) in tabs"
          :key="i"
          :class="{ 'tab__menu-item--active': activeTab === tab }"
          @click="activeTab = tab"
        >
          {{ tab }}
        </div>
      </div> -->
    <!-- <div class="tab__content"> -->

    <!-- <login v-if="activeTab === 'Login'"></login> -->
    <!-- <Register v-if="activeTab === 'Register'"></Register> -->
    <!-- <keep-alive>
          <component :is="activeTab" />
        </keep-alive> -->
    <!-- </div> -->
    <!-- </div> -->
  </div>
</template>
<script>
import HelloWorld from "./components/HelloWorld.vue";
import Login from "./components/Login.vue";
import Register from "./components/Register.vue";
import AboutMeCard from "./components/AboutMeCard.vue";
import TheComment from "./components/TheComment.vue";
export default {
  name: "App",

  data() {
    return {
      myComment: "",
      showDialog: false,
      notifications: [],
      tabs: ["Login", "Register", "AboutMeCard"],
      activeTab: "Login",
      aboutMe: "Md. Jahidul Islam Noman",
      aboutBody: "My Name Is Jahiudl Islam Noman . I am  programmer.",
      formData: {
        fullName: "",
        aboutYou: "",
        gender: "Male",
        language: "",
        skills: [],
        agreed: false,
        socialAccount: [],
      },
    };
  },

  provide() {
    return {
      about_title: this.aboutMe,
      about_body: this.aboutBody,
    };
  },
  mounted() {
    console.dir(this.$refs.normalComment);
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
    AboutMeCard,
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
.tab {
}
.tab__menu {
  display: flex;
}
.tab__menu-item {
  background-color: #dbdbdb;
  padding: 6px 15px;
  cursor: pointer;
}
.tab__menu-item--active {
  background-color: rgb(27, 104, 192);
  color: #ffff;
}
.ml-2 {
  margin-left: 11px;
}
</style>

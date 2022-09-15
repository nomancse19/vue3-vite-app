<template>
  <HelloWorld msg="Welcome To My Vue Js Site" class="hello"></HelloWorld>
  <div class="container">
    <h2>Credit Card Info</h2>
    <CreditCard></CreditCard>
  </div>
</template>
<script>
import HelloWorld from "./components/HelloWorld.vue";
import CreditCard from "./components/CreditCard.vue";
export default {
  name: "App",

  data() {
    return {
      nameOnCard: "",
      cardNumber: "",
      expiry: "",
      cvv: "",
    };
  },
  methods: {},
  components: {
    HelloWorld,
    CreditCard,
  },
};
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.container {
  padding: 22px;
}
</style>

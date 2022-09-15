<template>
  <HelloWorld msg="Welcome To My Vue Js Site" class="hello"></HelloWorld>
  <div class="container">
    <h2>Credit Card Info</h2>
    <credit-card
      v-model:nameOnCard="nameOnCard"
      v-model:cardNumber="cardNumber"
      v-model:expiry="expiry"
      v-model:cvv="cvv"
    ></credit-card>
    <br />
    <br />
    <br />
    <hr />
    <p>Name On Card : {{ nameOnCard }} <br /></p>
    <p>Card Number : {{ cardNumber }} <br /></p>
    <p>Expiry Date: {{ expiry }} <br /></p>
    <p>Card CVV : {{ cvv }} <br /></p>
  </div>
</template>
<script>
import HelloWorld from "./components/HelloWorld.vue";
import CreditCard from "./components/CreditCard.vue";
export default {
  name: "App",

  data() {
    return {
      nameOnCard: "Mr. ",
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
</style>

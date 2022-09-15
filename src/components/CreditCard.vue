<template>
  <div class="credit-card">
    <label for="">Enter Card Name </label>
    <input
      type="text"
      :value="nameOnCard"
      @input="handleInput('update:nameOnCard', $event)"
    />

    <label for="">Enter Card Number </label>
    <input
      type="text"
      :value="cardNumber"
      @input="handleInput('update:cardNumber', $event)"
    />

    <div class="row">
      <div class="col-6">
        <label for="">Expiry</label>
        <input
          type="text"
          placeholder="MM/YY"
          :value="expiry"
          @input="handleInput('update:expiry', $event)"
        />
      </div>

      <div class="col-6">
        <label for="">CVV</label>
        <input
          type="text"
          :value="cvv"
          @input="handleInput('update:cvv', $event)"
        />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    nameOnCard: {
      type: String,
      default: "",
    },
    cardNumber: {
      type: String,
      default: "",
    },
    expiry: {
      type: String,
      default: "",
    },
    cvv: {
      type: String,
      default: "",
    },
  },
  methods: {
    handleInput(eventName, e) {
      //console.log(e.target.value);
      this.$emit(eventName, e.target.value);
    },
  },
};
</script>

<style scoped>
.credit-card {
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
</style>

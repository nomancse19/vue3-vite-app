<template>
  <HelloWorld msg="Welcome To My Vue Js Site" class="hello"></HelloWorld>
  <about-me-card
    v-for="aboutInfo in about_data"
    :key="aboutInfo.name"
    :about_info="aboutInfo"
    @hide-title="HideTitle($event)"
  ></about-me-card>
  <product-card
    v-for="product in products"
    :key="product.name"
    :prop_product="product"
    @buy-now-click="clickBuy($event)"
    @add-to-cart="addtocart()"
    @toggle-favourite="handleToggleFavoutite($event)"
  ></product-card>
</template>
<script>
import HelloWorld from "./components/HelloWorld.vue";
import ProductCard from "./components/ProductCard.vue";
import AboutMeCard from "./components/AboutMeCard.vue";
export default {
  name: "App",

  data() {
    return {
      products: [
        {
          name: "Apple iPhone 13 Pro Max",
          thumbnail:
            "https://fdn2.gsmarena.com/vv/bigpic/apple-iphone-13-pro-max.jpg",
          price: 99850,
          addedToFavourite: true,
        },
        {
          name: "Xiaomi Redmi 11T Pro",
          thumbnail:
            "https://fdn2.gsmarena.com/vv/bigpic/xiaomi-redmi-note-11t-pro.jpg",
          price: 55800,
          addedToFavourite: false,
        },
        {
          name: "Xiaomi Redmi 10 Prime 2022",
          thumbnail: "https://fdn2.gsmarena.com/vv/bigpic/xiaomi-redmi-10-.jpg",
          price: 32500,
          addedToFavourite: false,
        },
      ],

      about_data: [
        {
          title: "About Of Noman",
          body: "Why do we use it It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop",
        },
        {
          title: "Education Of Noman",
          body: "Bsc In CSE. Software Training in Laravel, Zend Certified",
        },
      ],
    };
  },
  methods: {
    clickBuy(product_name) {
      console.log(product_name.name);
    },
    addtocart() {
      console.log("Add To Cart...");
    },
    handleToggleFavoutite(product) {
      product.addedToFavourite = !product.addedToFavourite;
    },
    HideTitle(aboutinfo) {
      aboutinfo.title = "********";

      //alert(aboutinfo.title);
    },
    KeyUpTest() {
      alert("Hello This Is Key Up Test");
    },
  },
  components: {
    HelloWorld,
    ProductCard,
    AboutMeCard,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
  text-align: center;
}
.hello {
  text-align: center;
}
button {
  padding: 5px 5px;
  margin: 5px;
  cursor: pointer;
}

.the-product__body img {
  height: 110px;
}
</style>

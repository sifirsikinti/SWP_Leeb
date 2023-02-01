<template>
  <section>
    <the-shop @add-order="createOrder"></the-shop>
    
  </section>
</template>

<script>
import TheShop from "./components/TheShop.vue";

export default {
  name: "App",
  components: {
    TheShop,
  },

  data() {
    return {
      orders: [],
    };
  },

  methods: {
    createOrder(email, phone, name, card) {
      fetch(
        "https://vue-shoppp-default-rtdb.europe-west1.firebasedatabase.app/orders.json",
        {
          method: "POST",
          headers: {
            "Content-Type": "application/json",
          },
          body: JSON.stringify({
            email: email,
            phone: phone,
            name: name,
            card: card,
          }),
        }
      )
        .then((response) => {
          console.log("response POST request", response);
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
};
</script>

<style>
body {
  background-color: lightblue;
}
</style>

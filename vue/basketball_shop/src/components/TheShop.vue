<template>
  <section>
    <h1 class="title">Basketball Shop</h1>
    <div class="pricing-table" v-if="shop">
      <div class="product">
        <h2 class="product-definition">Basketball</h2>
        <img src="../assets/basketball.png" class="product-img1" />
        <button @click="toggleShop" class="buttonShop">Buy</button>
      </div>
      <div class="product">
        <h2 class="product-definition">Schuhe</h2>
        <img src="../assets/schuh.jpg" class="product-img2" />
        <button @click="toggleShop" class="buttonShop">Buy</button>
      </div>
      <div class="product">
        <h2 class="product-definition">Trikot</h2>
        <img src="../assets/trikot.png" class="product-img3" />
        <button @click="toggleShop" class="buttonShop">Buy</button>
      </div>
    </div>
    <form v-if="!shop">
      <div class="header-order">
        <h2>Finish your order</h2>
      </div>
      <div class="inputs">
        <div>
          <input type="text" v-model="enteredMail" placeholder="e-Mail" />
        </div>
        <div>
          <input type="text" v-model="enteredPhone" placeholder="Phone" />
        </div>
        <div>
          <input type="text" v-model="enteredName" placeholder="Name" />
        </div>
        <div>
          <input type="text" v-model="cardNumber" placeholder="Card" />
        </div>
        <div>
          <button @click="createOrder" class="buttonOrder">Order</button>
        </div>
        <div>
          <button type="reset" class="buttonOrder">Clear</button>
        </div>
      </div>
    </form>
  </section>
</template>

<script>
export default {
  emits: ["add-order"],

  data() {
    return {
      shop: true,
      enteredMail: "",
      enteredPhone: "",
      enteredName: "",
      cardNumber: "",
    };
  },
  methods: {
    toggleShop() {
      this.shop = !this.shop;
    },
    createOrder() {
      this.$emit(
        "add-order",
        this.enteredMail,
        this.enteredPhone,
        this.enteredName,
        this.cardNumber
      );
      this.shop = !this.shop;
    },
  },
};
</script>

<style>
.title {
  text-align: center;
  font-size: 35px;
  margin-top: 0rem;
  color: black;
  margin-left: auto;
  margin-right: auto;
}

.header-order {
  text-align: center;
  font-size: 20px;
  margin-top: 0rem;
  color: white;
  text-shadow: 0 0 5px black;
}

img {
  margin-left: auto;
  margin-right: auto;
  margin-top: auto;
  margin-bottom: auto;
}

.product-img1 {
  max-width: 30%;
  height: auto;
  margin-top: auto;
  margin-bottom: auto;
}

.product-img2 {
  max-width: 100%;
  height: auto;
  margin-left: auto;
  margin-right: auto;
}

.product-img3 {
  max-width: 65%;
  height: auto;
  margin-left: auto;
  margin-right: auto;
}

.product {
  text-align: center;
  margin: 5rem;
  display: flex;
  flex-direction: column;
  background-color: white;
  box-shadow: 5px 5px 5px 5px black;
  width: 90%;
}

.product-definition {
  font-size: 20px;
  color: black;
  margin-bottom: 1rem;
  text-transform: uppercase;
}

.pricing-table {
  justify-content: center;
  display: flex;
}

button {
  display: flex;
  font: inherit;
  cursor: pointer;
  border: 1px solid white;
  background-color: black;
  color: white;
  margin-top: 0.5rem;
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
  justify-content: center;
  width: 500px;
}

.inputs {
  display: flex;
  flex-direction: column;
  align-items: center;
}

input {
  width: 500px;
  height: 20px;
  margin-top: 1rem;
}


@media screen and (max-width: 800px) {
  input {
    width: 100px;
    height: 10px;
    align-items: center;
    font-size: 3vw;
    font-size: 10px;
  }
  .buttonOrder {
    width: 100px;
    font-size: 10px;
  }
  .product {
    width: 200px;
    margin-right: auto;
    margin-left: auto;
    margin-top: 1rem;
  }
  .pricing-table {
    flex-direction: column;
  }
  .buttonShop {
    width: auto;
    font-size: 10px;
  }
  .product-img1 {
    width: 80px;
  }
  .product-img2 {
    width: 150px;
  }
  .product-img3 {
    width: 120px;
  }
  .product-definition {
    font-size: 10px;
  }
  .header-order {
    font-size: 15px;
  }
}
</style>

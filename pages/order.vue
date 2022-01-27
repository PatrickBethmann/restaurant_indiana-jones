<template>
  <div class="d-flex">
    <!-- section -->
    <div class="d-flex flex-wrap justify-content-evenly">
      <div v-for="(dish, index) in menu" :key="index">
        <div
          class="m-auto blur d-flex rounded-50 border-white flex-column justify-content-evenly align-items-center gap-2 w-75 h-75"
        >
          <b-img
            :src="dish.image"
            style="max-height: 50%; max-width: 100%; height: auto; width: auto"
          ></b-img>
          <p class="text-light h1">{{ dish.name }}</p>
          <p class="text-light h1">
            {{ dish.price.toString().replace('.', ',') }}€
          </p>
          <button
            type="button"
            class="btn btn-primary"
            @click="addItemToOrders(index)"
          >
            Hinzufügen
          </button>
        </div>
      </div>
    </div>

    <OrderList
      :placed-orders="placedOrders"
      @placeOrder="placeOrder()"
      @clearOrders="clearOrders()"
    />
  </div>
</template>

<script>
export default {
  data() {
    return {
      menu: [
        {
          name: 'Noodles',
          price: 2.49,
          image: 'https://cdn-icons-png.flaticon.com/512/2718/2718224.png',
        },
        {
          name: 'Soup',
          price: 1.99,
          image:
            'https://cdn-icons.flaticon.com/png/512/2387/premium/2387954.png?token=exp=1643281638~hmac=e1d722fdb83dc429b8d39a1d1077f306',
        },
        {
          name: 'Fish',
          price: 4.99,
          image:
            'https://cdn-icons.flaticon.com/png/512/2346/premium/2346909.png?token=exp=1643281672~hmac=1af497e6f69e0a2b8e8fea167d795e77',
        },
        {
          name: 'Ice',
          price: 2.49,
          image: 'https://cdn-icons-png.flaticon.com/512/938/938114.png',
        },
        {
          name: 'Hamburger',
          price: 2.99,
          image: 'https://cdn-icons-png.flaticon.com/512/3075/3075929.png',
        },
      ],
      placedOrders: [],
    }
  },

  watch: {
    // Keeps the localStorage up to date
    placedOrders() {
      localStorage.setItem('placedOrders', JSON.stringify(this.placedOrders))
    },
  },
  mounted() {
    // Loading stored orders
    if (localStorage.placedOrders) {
      this.placedOrders = JSON.parse(
        localStorage.getItem('placedOrders') || '[]'
      )
    }
  },
  methods: {
    addItemToOrders(index) {
      this.placedOrders.push(this.menu[index])
    },
    clearOrders() {
      this.placedOrders = []
    },
    placeOrder() {
      alert('Vielen Danke für Ihre Bestellung')
    },
  },
}
</script>

<style></style>

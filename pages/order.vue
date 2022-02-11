<template>
  <div class="d-flex">
    <!-- section -->
    <div class="d-flex flex-wrap justify-content-evenly">
      <div v-for="(dish, index) in menu" :key="index">
        <DishCard :dish="dish" @addItemToOrders="addItemToOrders(index)" />
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
          image: 'https://cdn-icons-png.flaticon.com/512/454/454570.png',
        },
        {
          name: 'Fish',
          price: 4.99,
          image: 'https://cdn-icons-png.flaticon.com/512/3280/3280126.png',
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
      alert('Vielen Dank für Ihre Bestellung')
      this.placedOrders = []
    },
  },
}
</script>

<style></style>

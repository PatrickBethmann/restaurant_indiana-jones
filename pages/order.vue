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

    <div
      v-if="placedOrders.length > 0"
      id="order-list"
      class="border-white text-center rounded-50 blur w-25 text-light p-5"
      style="margin-right: 25px; height: fit-content"
    >
      <div class="h2">Bestellungen</div>
      <ul></ul>
      <li
        v-for="(order, index) in placedOrders"
        :key="index"
        class="d-flex justify-content-between"
      >
        <div>{{ order.name }}</div>

        <div class="float-right">
          {{ order.price.toString().replace('.', ',') }}€
        </div>
      </li>
      <div class="mt-3">
        Gesamtpreis: {{ totalPrice.toString().replace('.', ',') }}€
      </div>
      <button
        type="button"
        class="btn btn-primary"
        style="margin-bottom: -50px"
        @click="placeOrder()"
      >
        Bestellen
      </button>
      <button
        type="button"
        class="btn btn-danger"
        style="margin-bottom: -50px"
        @click="clearOrders()"
      >
        Zurücksetzen
      </button>
    </div>
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
            'https://cdn-icons.flaticon.com/png/512/2387/premium/2387954.png?token=exp=1643264684~hmac=419e0f5cda4d71099f5e91382b1c1a2c',
        },
        {
          name: 'Fish',
          price: 4.99,
          image:
            'https://cdn-icons.flaticon.com/png/512/2346/premium/2346909.png?token=exp=1643264710~hmac=bd04ef8a0a3a7a8472939cd4597040f1',
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
  computed: {
    totalPrice() {
      let price = 0
      for (const order of this.placedOrders) {
        price += order.price
      }

      return Math.round(price * 100) / 100
    },
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
      alert('Vielen Danke für deine Bestellung')
      this.clearOrders()
    },
  },
}
</script>

<style></style>

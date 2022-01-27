<template>
  <div>
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
          <button
            type="button"
            class="btn btn-primary"
            @click="orderItem(index)"
          >
            Bestellen
          </button>
        </div>
      </div>
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
          image: 'https://cdn-icons-png.flaticon.com/512/2718/2718224.png',
        },
        {
          name: 'Soup',
          image:
            'https://cdn-icons.flaticon.com/png/512/2387/premium/2387954.png?token=exp=1643264684~hmac=419e0f5cda4d71099f5e91382b1c1a2c',
        },
        {
          name: 'Fish',
          image:
            'https://cdn-icons.flaticon.com/png/512/2346/premium/2346909.png?token=exp=1643264710~hmac=bd04ef8a0a3a7a8472939cd4597040f1',
        },
        {
          name: 'Ice',
          image: 'https://cdn-icons-png.flaticon.com/512/938/938114.png',
        },
      ],
      placedOrders: [],
    }
  },
  methods: {
    orderItem(index) {
      this.placedOrders.push(this.menu[index].name)
      alert(this.placedOrders)
    },
  },
}
</script>

<style></style>

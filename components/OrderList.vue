<template>
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
      @click="$emit('placeOrder')"
    >
      Bestellen
    </button>
    <button
      type="button"
      class="btn btn-danger"
      style="margin-bottom: -50px"
      @click="$emit('clearOrders')"
    >
      Zurücksetzen
    </button>
  </div>
</template>

<script>
export default {
  props: {
    placedOrders: {
      type: Array,
      default: null,
    },
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
  methods: {},
}
</script>

<style></style>

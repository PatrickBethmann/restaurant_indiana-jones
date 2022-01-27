<template>
  <div
    class="m-auto blur d-flex rounded-50 border-white flex-column justify-content-evenly align-items-center gap-2 w-75 h-75"
  >
    <b-img
      :src="dish.image"
      style="max-height: 50%; max-width: 100%; height: auto; width: auto"
    ></b-img>
    <p class="text-light h1">{{ dish.name }}</p>
    <p class="text-light h1">{{ dish.price.toString().replace('.', ',') }}€</p>
    <button
      type="button"
      class="btn btn-primary"
      @click="$emit('addItemToOrders', index)"
    >
      Hinzufügen
    </button>
  </div>
</template>

<script>
export default {
  props: {
    dish: {
      type: Object,
      default: null,
    },
  },
}
</script>

<style></style>

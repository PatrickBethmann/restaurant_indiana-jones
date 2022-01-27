<template>
  <b-card
    :title="entry.name"
    tag="article"
    style="width: 52%; margin: auto; background-color: rgba(0, 0, 0, 0.25)"
    class="mb-2 text-center blur text-light border-white"
  >
    <b-card-text class="">
      Datum: {{ entry.date }}
      <br />
      Uhrzeit: {{ entry.time }}
    </b-card-text>
  </b-card>
</template>

<script>
export default {
  props: {
    entry: {
      type: Object,
      default: null,
    },
  },
}
</script>

<style></style>

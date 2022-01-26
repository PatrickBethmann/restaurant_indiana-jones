<template>
  <b-card
    :title="entry.name"
    tag="article"
    style="width: 51%; margin: auto"
    class="mb-2 text-center"
  >
    <b-card-text>
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

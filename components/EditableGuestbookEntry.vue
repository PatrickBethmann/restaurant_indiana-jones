<template>
  <b-card
    tag="article"
    style="width: 52%; margin: auto; background-color: rgba(0, 0, 0, 0.25)"
    class="mb-2 text-center blur text-light border-white rounded-50"
  >
    <span>Name:</span>
    <b-input
      id="name"
      v-model="name"
      class="bg-dark text-light"
      placeholder="Name"
    />
    <span>Nachricht:</span>
    <b-input
      id="message"
      v-model="message"
      class="bg-dark text-light"
      type="text"
      placeholder="Nachricht"
    />
    <!-- <span>Datum:</span>
    <b-input
      id="date"
      v-model="date"
      class="bg-dark text-light"
      type="date"
      placeholder="Datum"
    />
    <span>Uhrzeit:</span>
    <b-input
      id="time"
      v-model="time"
      class="bg-dark text-light"
      type="time"
      placeholder="Uhrzeit"
    /> -->

    <b-button variant="outline-primary" @click="deleteEntry()">Delete</b-button>
    <b-button variant="outline-success" @click="saveEntry()"
      >Speichern</b-button
    >
  </b-card>
</template>

<script>
export default {
  props: {
    entry: {
      type: Object,
      default: null,
    },
    index: {
      type: Number,
      default: null,
    },
  },
  data() {
    return {
      name: '',
      message: '',
      date: '',
      time: '',
    }
  },
  mounted() {
    this.name = this.entry.name
    this.message = this.entry.message
    this.date = this.entry.date
    this.time = this.entry.time
  },
  methods: {
    deleteEntry() {
      this.$emit('deleteEntry', this.index)
    },
    saveEntry() {
      this.$emit(
        'updateEntry',
        {
          name: this.name,
          message: this.message,
          date: this.date,
          time: this.time,
        },
        this.index
      )
    },
  },
}
</script>

<style></style>

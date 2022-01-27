<template>
  <div class="column text-center">
    <b-button v-b-modal.guestbookModal class="w-25 mt-2 mb-2"
      >Neuer Eintrag</b-button
    >

    <GuestbookEntry
      v-for="entry in guestbookEntries"
      :key="entry.id"
      :entry="entry"
    />

    <b-modal
      id="guestbookModal"
      title="Neuer Gästebucheintrag"
      @show="resetModal"
      @hidden="resetModal"
      @ok="handleOk"
    >
      <form ref="form" @submit.stop.prevent="handleSubmit">
        <!-- Name -->
        <b-form-group
          label="Name"
          label-for="name-input"
          invalid-feedback="Name ist erforderlich"
          :state="nameState"
        >
          <b-form-input
            id="name-input"
            v-model="name"
            :state="nameState"
            required
          ></b-form-input>
        </b-form-group>

        <!-- Message -->
        <b-form-group
          label="Nachricht"
          label-for="message-input"
          :state="messageState"
        >
          <b-form-input
            id="message-input"
            v-model="message"
            :state="messageState"
          ></b-form-input>
        </b-form-group>
      </form>
    </b-modal>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: '',
      nameState: null,
      message: '',
      guestbookEntries: [],
    }
  },
  watch: {
    // Keeps the localStorage up to date
    guestbookEntries() {
      localStorage.setItem('guestbook', JSON.stringify(this.guestbookEntries))
    },
  },
  mounted() {
    // Loading stored guestbook entries
    if (localStorage.guestbook) {
      this.guestbookEntries = JSON.parse(
        localStorage.getItem('guestbook') || '[]'
      )
    }
  },

  methods: {
    checkFormValidity() {
      if (this.name) {
        this.nameState = true
      } else {
        this.nameState = false
      }
      if (this.nameState) {
        return true
      }
      return false
    },
    resetModal() {
      this.name = ''
      this.nameState = null
    },
    handleOk(bvModalEvt) {
      // Prevent modal from closing
      bvModalEvt.preventDefault()

      // Trigger submit handler
      this.handleSubmit()
    },
    handleSubmit() {
      // Exit when the form isn't valid
      if (!this.checkFormValidity()) {
        return
      }
      // create new entry in guestbookEntries array
      this.createEntry()
    },
    createEntry() {
      const date = new Date()
      const currentDate = date.toLocaleDateString()
      const currentTime = `${
        date.getHours() < 10 ? '0' : ''
      }${date.getHours()}:${date.getMinutes()} Uhr`
      const newEntry = {
        name: this.name,
        message: this.message,
        date: currentDate,
        time: currentTime,
      }
      this.guestbookEntries.push(newEntry)
    },
  },
}
</script>

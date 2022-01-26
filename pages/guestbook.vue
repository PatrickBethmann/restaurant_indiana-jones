<template>
  <div>
    <b-button v-b-modal.guestbookModal>Neuer Eintrag</b-button>

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
        <!-- Datum -->
        <b-form-group
          label="Datum"
          label-for="date-input"
          invalid-feedback="Datum ist erforderlich"
          :state="dateState"
        >
          <b-form-datepicker
            id="date-input"
            v-model="date"
            :state="dateState"
            placeholder="Datum auswählen"
            required
          ></b-form-datepicker>
        </b-form-group>
        <!-- Uhrzeit -->
        <b-form-group
          label="Uhrzeit"
          label-for="time-input"
          invalid-feedback="Uhrzeit ist erforderlich"
          :state="timeState"
        >
          <b-form-timepicker
            id="time-input"
            v-model="time"
            :state="timeState"
            placeholder="Uhrzeit auswählen"
            required
          ></b-form-timepicker>
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
      submittedNames: [],
      date: '',
      dateState: null,
      submittedDates: [],
      time: '',
      timeState: null,
      submittedTimes: [],
    }
  },

  methods: {
    checkFormValidity() {
      // const valid = this.$refs.form.checkValidity()
      // console.log(valid)
      // this.nameState = valid
      // this.dateState = valid
      // this.timeState = valid
      if (this.name) {
        this.nameState = true
      } else {
        this.nameState = false
      }
      if (this.date) {
        this.dateState = true
      } else {
        this.dateState = false
      }
      if (this.time) {
        this.timeState = true
      } else {
        this.timeState = false
      }
      if (this.nameState && this.dateState && this.timeState) {
        return true
      }
      return false
    },
    resetModal() {
      this.name = ''
      this.nameState = null
      this.date = ''
      this.dateState = null
      this.time = ''
      this.timeState = null
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
      // Push the name, date and time to submitted arrays
      this.submittedNames.push(this.name)
      this.submittedDates.push(this.date)
      this.submittedTimes.push(this.time)
    },
  },
}
</script>

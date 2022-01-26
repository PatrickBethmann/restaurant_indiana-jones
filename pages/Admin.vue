<template>
  <div class="column text-center">
    <b-form
      v-if="!loggedIn"
      class="w-50 m-auto blur p-5 rounded-pill overflow-hidden text-light"
      @submit="onSubmit"
      @reset="onReset"
    >
      <!-- Username -->
      <b-form-group
        id="input-group-1"
        label="Benutzername:"
        label-for="usernameInput"
      >
        <b-form-input
          id="usernameInput"
          v-model="form.username"
          type="text"
          placeholder="Benutzername..."
          :state="validateUsername"
          required
        ></b-form-input>
        <b-form-invalid-feedback :state="validateUsername">
          Dein Benutzername muss 5-12 Zeichen lang sein.
        </b-form-invalid-feedback>
      </b-form-group>

      <!-- Password -->
      <b-form-group
        id="input-group-2"
        label="Passwort:"
        label-for="passwordInput"
      >
        <b-form-input
          id="passwordInput"
          v-model="form.password"
          placeholder="Passwort..."
          type="password"
          :state="validatePassword"
          required
        ></b-form-input>
        <b-form-invalid-feedback :state="validateUsername">
          Dein Passwort muss mindestens 5 Zeichen lang sein.
        </b-form-invalid-feedback>
      </b-form-group>

      <b-button type="submit" variant="primary">Login</b-button>
    </b-form>

    <div v-if="loggedIn" id="giestbook-entries">
      <EditableGuestbookEntry
        v-for="(entry, index) in guestbookEntries"
        :key="index"
        :index="index"
        :entry="entry"
        @deleteEntry="deleteEntry"
        @updateEntry="updateEntry"
      />
    </div>

    <b-button
      v-if="loggedIn"
      class="w-25 mt-2 mb-2 text-dark bg-light"
      @click="loggedIn = false"
      >Log out</b-button
    >
  </div>
</template>

<script>
export default {
  data() {
    return {
      username: 'Admin',
      password: '12345',
      guestbookEntries: [],
      form: {
        username: '',
        password: '',
      },
      loggedIn: false,
    }
  },
  computed: {
    validateUsername() {
      return this.form.username.length > 4 && this.form.username.length < 13
    },
    validatePassword() {
      return this.form.password.length > 4
    },
  },
  watch: {
    // Keeps the login status up to date
    loggedIn() {
      localStorage.setItem('loggedIn', JSON.stringify(this.loggedIn))
    },
    // Keeps the localStorage up to date
    guestbookEntries() {
      localStorage.setItem('guestbook', JSON.stringify(this.guestbookEntries))
    },
  },
  mounted() {
    if (localStorage.loggedIn) {
      this.loggedIn = JSON.parse(localStorage.getItem('loggedIn') || 'false')
    }
    if (localStorage.guestbook) {
      this.guestbookEntries = JSON.parse(
        localStorage.getItem('guestbook') || '[]'
      )
    }
  },
  methods: {
    onSubmit(event) {
      event.preventDefault()
      if (this.checkLogin(this.form.username, this.form.password)) {
        this.loggedIn = true
      }

      this.onReset(event)
    },
    onReset(event) {
      event.preventDefault()
      // Reset our form values
      this.form.username = ''
      this.form.password = ''
    },
    checkLogin(username, password) {
      if (typeof username === 'string') {
        username.toLowerCase()
      } else {
        return false
      }
      if (
        username === this.username.toLowerCase() &&
        password === this.password
      ) {
        return true
      } else {
        return false
      }
    },
    deleteEntry(index) {
      this.guestbookEntries.splice(index, 1)
    },
    updateEntry(updatedEntry, index) {
      this.guestbookEntries[index] = updatedEntry
      localStorage.setItem('guestbook', JSON.stringify(this.guestbookEntries))
    },
  },
}
</script>

<style></style>

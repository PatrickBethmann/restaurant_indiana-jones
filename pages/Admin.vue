<template>
  <div class="column text-center">
    <b-form
      v-if="!loggedIn"
      class="w-50 m-auto"
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
          required
        ></b-form-input>
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
          required
        ></b-form-input>
      </b-form-group>

      <b-button type="submit" variant="primary">Login</b-button>
    </b-form>

    <div v-if="loggedIn" id="giestbook-entries">
      <GuestbookEntry
        v-for="entry in guestbookEntries"
        :key="entry.id"
        :entry="entry"
      />
    </div>

    <b-button
      v-if="loggedIn"
      class="w-25 mt-2 mb-2 text-danger"
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
      form: {
        username: '',
        password: '',
      },
      loggedIn: false,
    }
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
      console.log('hi')
      console.log(this.loggedIn)
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
        alert('Succes')
        return true
      } else {
        alert('wrong input')
        return false
      }
    },
  },
}
</script>

<style></style>

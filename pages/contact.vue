<template>
  <div class="container">
    <div class="contacts"></div>
    <fieldset disabled>
      <form class="contact-form" action="">
        <label for="firstname">Vorname</label>
        <input
          id="firstname"
          type="text"
          name="firstname"
          placeholder="Dein Name.."
        />

        <label for="lastname">Nachname</label>
        <input
          id="lastname"
          type="text"
          name="lastname"
          placeholder="Dein Nachname.."
        />

        <label for="message">Nachricht</label>
        <textarea
          id="message"
          name="message"
          placeholder="Deine Nachricht.."
          style="height: 200px"
        ></textarea>

        <input type="submit" value="Submit" />
      </form>
    </fieldset>
    <div class="links">
      <a href="mailto:indiana.jones@notexisting.com">Email</a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ContactPage',
}
</script>

<style scoped>
.contact-form {
  width: 100%;
  margin: 20px auto;
  border-radius: 5px;
}

input[type='text'],
textarea {
  width: 100%;
  padding: 12px;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
  margin-top: 6px;
  margin-bottom: 16px;
  resize: vertical;
}

input[type='submit'] {
  background-color: #04aa6d;
  color: white;
  padding: 12px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}
input[type='submit']:hover {
  background-color: #45a049;
}

.links {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;

  margin-top: 20px;
}
.links a {
  font-size: 2rem;
  text-decoration: underline;
  color: black;
}
</style>

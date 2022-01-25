<template>
  <div class="wrapper">
    <header>
      <h1 class="title">McJones</h1>
    </header>
    <nav>
      <NuxtLink to="/" class="link">Startseite</NuxtLink>
      <NuxtLink to="/contact" class="link">Kontakt</NuxtLink>
      <NuxtLink to="/history" class="link">Geschichte</NuxtLink>
    </nav>
  </div>
</template>

<script>
export default {
  name: 'Header',
}
</script>

<style scoped>
header {
  background-color: gray;
  height: 100px;

  display: flex;
  justify-content: center;
  align-items: center;
}

header h1 {
  text-transform: uppercase;
  text-align: center;
  color: #fff;
  line-height: 50px;
}

nav {
  background-color: lightgray;
  height: 50px;

  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  align-items: center;
}

.link {
  text-transform: uppercase;
  text-decoration: none;
  color: black;
}
.nuxt-link-exact-active {
  font-weight: bold;
}
</style>

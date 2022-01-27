<template>
  <footer class="bg-dark border-top">
    <NuxtLink to="/contact" class="link-light">Kontakt</NuxtLink>
  </footer>
</template>

<script>
export default {}
</script>

<style scoped>
footer {
  width: 100%;
  height: 75px;

  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  align-content: center;

  margin-top: auto;
}
footer a {
  display: flex;
  font-size: 1.5rem;
  align-items: center;
}
</style>

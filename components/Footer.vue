<template>
  <footer>
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
  background: gray;

  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  align-content: center;
}
footer a {
  display: flex;
  font-size: 1.5rem;
  align-items: center;
}
</style>

<template>
  <footer>
    <NuxtLink to="/contact" class="link">Kontakt</NuxtLink>
  </footer>
</template>

<script>
export default {}
</script>

<style scoped>
footer {
  width: 100%;
  height: 50px;
  background: rgba(0, 0, 0, 0.2);

  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  align-content: center;
}
footer a {
  color: black;
  display: flex;
  align-items: center;
}
</style>

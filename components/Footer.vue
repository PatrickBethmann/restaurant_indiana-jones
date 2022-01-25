<template>
  <footer>
    <a href="">Impressum</a>
    <a href="">Kontakt</a>
  </footer>
</template>

<script>
export default {}
</script>

<style scoped>
footer {
  position: absolute;
  bottom: 0px;
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

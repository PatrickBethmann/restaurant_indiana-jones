<template>
  <div id="app">
    <Header />
    <Nuxt />
    <Footer id="footer" />
  </div>
</template>

<style>
#app {
  min-height: 100vh;

  display: flex;
  flex-direction: column;
  justify-content: flex-start;
}

#footer {
  margin-top: auto;
}
</style>

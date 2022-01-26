<template>
  <div id="app" class="bg-image">
    <Header />
    <Nuxt />
    <Footer />
  </div>
</template>

<style>
#app {
  min-height: 100vh;

  display: flex;
  flex-direction: column;
  justify-content: flex-start;

  background-image: url('https://cdn.pixabay.com/photo/2021/02/08/07/39/chef-5993951_960_720.jpg');
  background-repeat: no-repeat;
  background-size: cover;
}
</style>

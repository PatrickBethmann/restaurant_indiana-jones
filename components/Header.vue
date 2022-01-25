<template>
  <div>
    <!-- Navbar -->
    <nav class="navbar navbar-expand-sm navbar-light">
      <div class="container-fluid">
        <div id="navbarExample01">
          <ul class="navbar-nav me-auto mb-2 mb-lg-0">
            <li class="nav-item active">
              <NuxtLink class="nav-link" aria-current="page" to="/"
                >Wilkommen</NuxtLink
              >
            </li>
            <li class="nav-item">
              <NuxtLink class="nav-link" to="/contact">Kontakt</NuxtLink>
            </li>
            <li class="nav-item">
              <NuxtLink class="nav-link" to="/history">Geschichte</NuxtLink>
            </li>
            <li class="nav-item">
              <NuxtLink class="nav-link" to="/guestbook">Gästebuch</NuxtLink>
            </li>
          </ul>
        </div>
      </div>
    </nav>
    <!-- Navbar -->

    <!-- Background image -->
    <div
      class="p-5 text-center bg-image"
      :style="{
        'background-image': `url('https://cdn.pixabay.com/photo/2013/12/31/21/47/restaurant-237060_960_720.jpg')`,
        height: '400px',
      }"
    >
      <div class="mask" style="background-color: rgba(0, 0, 0, 0.6)">
        <div class="d-flex justify-content-center align-items-center h-100">
          <div class="text-white">
            <h1 class="mb-3">McJones</h1>
            <h4 class="mb-3">Kulinarische Leckereien</h4>
          </div>
        </div>
      </div>
    </div>
    <!-- Background image -->
  </div>
</template>

<script>
export default {
  name: 'Header',
}
</script>

<style scoped>
/* header {
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
} */
</style>

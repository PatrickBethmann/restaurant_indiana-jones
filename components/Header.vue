<template>
  <div>
    <!-- Navbar -->
    <nav class="navbar navbar-expand-sm navbar-dark bg-dark">
      <div class="container-fluid">
        <div id="navbarExample01" class="w-100">
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
            <li class="nav-item">
              <NuxtLink class="nav-link" to="/order">Order</NuxtLink>
            </li>
            <li class="nav-item ms-auto">
              <NuxtLink class="nav-link" to="/admin">Admin</NuxtLink>
            </li>
          </ul>
        </div>
      </div>
    </nav>
    <!-- Navbar -->

    <div class="text-center bg-image border-bottom" :style="{}">
      <div
        class="mask blur"
        style="background-color: rgba(0, 0, 0, 0.2); height: 250px"
      >
        <div class="d-flex justify-content-center align-items-center h-100">
          <div class="text-white">
            <h1 class="mb-3">McJones</h1>
            <h4 class="mb-3">Kulinarische Leckereien</h4>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header',
}
</script>

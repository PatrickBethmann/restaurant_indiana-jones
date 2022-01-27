<template>
  <div class="main">
    <div class="header text-light border-white blur rounded-50 p-5">
      <div class="headerLeft">
        <h2 class="headerTitle h1">McJones</h2>
        <p class="headerDescription h2">
          Wilkommen auf unserer Website! In unserem Restaurant gibt es viele
          leckere Gerichte!
        </p>

        <div class="headerDescription h2">
          <p class="h2 mt-4">Öffnungszeiten</p>
          <p class="h3">Montag - Freitag</p>
          <p class="h4">
            08:00 Uhr - 12:00 Uhr <br />
            13:30 Uhr - 18:30 Uhr
          </p>
          <br class="h4" />
        </div>
      </div>
      <div class="headerRight">
        <img
          class="border border-white border m-auto rounded-circle"
          style=""
          src="https://www.seekpng.com/png/full/45-452520_harrison-ford-png-indiana-jones-png.png"
          alt="Picture of Indiana Jones"
        />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
}
</script>

<style>
.main {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.header {
  /* Position */
  padding: 10px;
  height: 400px;
  width: 85%;

  /* Design */

  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}

.headerLeft,
.headerRight {
  width: 50%;
  margin: auto;
  height: 100%;
  text-align: center;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.headerRight img {
  object-fit: contain;
  width: 300px;
  height: 300px;
}
</style>

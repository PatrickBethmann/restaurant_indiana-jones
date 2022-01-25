<template>
  <div>
    <h1>Startseite</h1>
    <div class="header">
      <div class="headerLeft">
        <h2 class="headerTitle">McJones</h2>
        <p class="headerDescription">
          Wilkommen auf meiner Website! In meinem Restaurant gibt es viele
          leckere Gerichte!
        </p>
      </div>
      <div class="headerRight">
        <img src="/profile-picture.png" alt="Bild" />
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
.header {
  /* Position */
  margin: auto;
  padding: 10px;
  height: 350px;
  width: 85%;

  /* Design */
  border-radius: 20px;
  background-color: lightcoral;

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
  justify-content: flex-start;
}

.headerTitle {
  font-size: 3rem;
}
.headerDescription {
  font-size: 2rem;
}

.headerRight img {
  object-fit: contain;
  max-width: 100%;
  max-height: 100%;
  width: auto;
  height: auto;
}
</style>

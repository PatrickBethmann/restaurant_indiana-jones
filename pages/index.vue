<template>
  <div class="main">
    <div class="header text-light blur rounded-50">
      <div class="headerLeft">
        <h2 class="headerTitle">McJones</h2>
        <p class="headerDescription">
          Wilkommen auf unserer Website! In unserem Restaurant gibt es viele
          leckere Gerichte!
        </p>
      </div>
      <div class="headerRight">
        <img
          src="~/assets/images/profile-picture.png"
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
  width: 100%;
  /* Position */
  padding: 10px;
  height: 350px;
  width: 85%;

  /* Design */
  border-radius: 30px;
  background-color: rgba(0, 0, 0, 0.25);

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

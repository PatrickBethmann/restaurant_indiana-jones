<template>
  <div class="flex-column m-auto align-items-center" stlye="padding: 48px">
    <h1>Unsere Geschichte</h1>
    <div class="vtl">
      <div class="event">
        <strong class="edate">1. Juli 1899</strong>
        <p class="etxt">Geburt des Geschäftsführers in Princeton, New Jersey</p>
      </div>
      <div class="event">
        <strong class="edate">11 November 2021</strong>
        <p class="etxt">Aus Langeweile eine Restaurant gegründet.</p>
      </div>
      <div class="event">
        <strong class="edate">27 Januar 2022</strong>
        <p class="etxt">Eigene Website erblickt das Licht der Welt!</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HistoryPage',
}
</script>

<style scoped>
/* (A) "SET" THE TIMELINE CONTAINER */
.vtl {
  /* (A1) RELATIVE POSITION NECESSARY TO PROPERLY POSITION TIMELINE LATER */
  position: relative;
  /* (A2) RESERVE MORE SPACE TO THE LEFT FOR THE TIMELINE */
  padding: 10px 10px 10px 50px;
  /* (A3) OPTIONAL WIDTH RESTRICTION */
  max-width: 400px;
}

/* (B) DRAW TIMELINE USING ::BEFORE */
.vtl::before {
  /* (B1) DRAW THE TIMELINE */
  content: '';
  width: 5px;
  background-color: #de421a;
  /* (B2) POSITION IT TO THE LEFT */
  position: absolute;
  top: 0;
  bottom: 0;
  left: 15px;
}

/* (C) STYLES FOR THE EVENTS */
div.event {
  padding: 20px 30px;
  background-color: #ffebeb;
  position: relative;
  border-radius: 6px;
  margin-bottom: 10px;
}

/* (D) STYLES FOR THE DATE & TEXT */
strong.edate {
  font-size: 1.1em;
  font-weight: bold;
  color: #ff6a00;
}
p.etxt {
  margin: 10px 0 0 0;
  color: #222;
}

/* (E) ADD "SPEECH BUBBLE TRIANGLE" TO THE EVENTS */
div.event::before {
  content: '';
  border: 10px solid transparent;
  border-right-color: #ffebeb;
  border-left: 0;
  position: absolute;
  top: 20%;
  left: -10px;
}

/* (F) ADD A CIRCLE ON THE TIMELINE TO INDICATE AN EVENT */
div.event::after {
  content: '';
  background: #fff;
  border: 4px solid #de421a;
  width: 16px;
  height: 16px;
  border-radius: 50%;
  position: absolute;
  top: 20%;
  left: -44px;
}

/* (X) DOES NOT MATTER */
html,
body {
  font-family: arial, sans-serif;
}
</style>

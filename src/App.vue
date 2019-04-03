<template>
  <div id="app">
    <div class="wrapper">
      <div class="title">Ты сегодня покормил кота?</div>
      <div class="cards">
        <Card color="#1698d9" product_name='fua-gra'>
          <template slot="product_dose"></template>
          <template slot="weight">0.5</template>
        </Card>
        <Card color="#d91667" product_name='fish'>
          <template slot="product_dose"></template>
           <template slot="weight">2</template>
           </Card>
        <Card color="#b3b3b3" product_name='chicken' disabled=True >
          <template slot="product_dose"></template>
          <template slot="weight">5</template>
        </Card>
      </div>
    </div>
  </div>
</template>

<script>
import Card from "./components/Card";

export default {
  name: "App",
  components: {
    Card
  }
};
</script>

<style>
@import url(
  'https://fonts.googleapis.com/css?family=Exo+2:500,600,700,800&subset=latin,cyrillic');
@import url('https://fonts.googleapis.com/css?family=Exo+2:100&subset=cyrillic');

html,
body {
  height: 100%;
  margin: 0;
  padding: 0;
}

body {
  background-image: url("https://drive.google.com/uc?id=1Lc65WGEN_K-RzHET5tC-E0biKZvc6QXU");
  display: flex;
  font-family: "Exo 2", sans serif;
}

.wrapper {
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.wrapper > div {
  flex-basis: 1 0 auto;
  margin: 15px 40px;
}
.wrapper > .title {
  color: white;
  text-align: center;
  font-size: 36px;
  font-weight: 100;
}

.cards {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
}
.cards > div {
  flex-basis: 320px;
  margin: 15px 40px;
  cursor: pointer;
}
</style>

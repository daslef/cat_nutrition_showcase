<template>
  <div id="app">
    <div class="wrapper">
      <div class="title">Ты сегодня покормил кота?</div>
      <div class="cards">
        <Card color="#767676">
          <template slot="product_taste">с салями</template>
          <template slot="product_dose"></template>
          <template slot="product_gifts">шуршалка</template>
          <template slot="weight">2</template>
        </Card>
        <Card color="#727236"/>
        <Card color="#38FE65">
          <template slot="product_taste">с лососем</template>
          <template slot="product_dose"></template>
          <template slot="product_gifts">5 мышек</template>
          <template slot="weight">2</template>
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
  https://fonts.googleapis.com/css?family=Exo+2:500,600,700,800&subset=latin,cyrillic);

html,
body {
  height: 100%;
  margin: 0;
  padding: 0;
}

body {
  background-image: url("https://drive.google.com/uc?id=1Lc65WGEN_K-RzHET5tC-E0biKZvc6QXU");
  display: border-box;
  font-family: "Exo 2", sans serif;
}

.wrapper {
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.wrapper > div {
  flex-basis: 1 0 auto;
  margin: 15px 40px;
}
.wrapper > .title {
  color: white;
  text-align: center;
  font-size: 36px;
  font-weight: 400;
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

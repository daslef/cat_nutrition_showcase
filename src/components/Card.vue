<template>
  <div
    class="card"
    :class="{selected: cardToggler}"
    @click="cardToggler=!cardToggler"
  >
    <div class="bg"></div>
    <div class="card-content">
      <p class="text-16">Сказочное заморское яство</p>
      <p class="text-bold text-48">Нямушка</p>
      <p class="text-bold text-24">
        <slot name="product_taste">с фуа-гра</slot>
      </p>
      <p class="text-14">
        <b>
          <slot name="product_dose">10</slot>
        </b> порций
        <br>
        <b>
          <slot name="product_gifts">мышь</slot>
        </b> в подарок
      </p>
    </div>
    <img
      src="https://drive.google.com/uc?id=1j0G2FJWu6CGpSWr2tYm5_GSGCCVs1L4h"
      id="cat-pic"
      alt="cat picture"
    >
    <div class="round-shape" :style="{backgroundColor:color}">
      <span class="mass">
        <slot name="weight">0,5</slot>
      </span>
      <br>
      <span>КГ</span>
    </div>
  </div>
</template>

<script>
export default {
  props: ["color"],
  data: function() {
    return {
      cardToggler: false,
      hover: false
    };
  }
};
</script>

<style scoped>
.card {
  height: 480px;
  /*   height: 502px; */
  width: 320px;
  clip-path: polygon(15% 0%, 100% 0%, 100% 100%, 0% 100%, 0% 10%);
  border: 4px solid #1698d9;
  border-radius: 10px;
  border-top-left-radius: 0px;
  background-color: #f2f2f2;
  overflow: hidden;
}

.card .card-content {
  height: 207px;
  margin: 24px 0 0 49px;
}
.card .round-shape {
  position: relative;
  bottom: 220px;
  left: 220px;
  height: 81px;
  width: 81px;
  border-radius: 50%;
  color: white;
  text-align: center;
}
.card #cat-pic {
  width: 370px;
  height: 361px;
  position: relative;
  right: 24px;
}
.card .mass {
  position: relative;
  top: 8px;
  font-size: 40px;
  line-height: 52px;
}

.selected {
  border: 4px solid #ee3355;
}

.text-bold {
  font-weight: 600;
  color: black;
  margin: 0;
}

.text-48 {
  font-size: 48px;
}

.text-24 {
  font-size: 24px;
}

.text-14 {
  font-size: 14px;
  color: #666666;
  margin: 16px 0 0 0;
}

.text-16 {
  font-size: 16px;
  color: #666666;
  margin-bottom: 15px;
}
</style>
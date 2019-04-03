У<template>
  <div>
    <div
      class="card"
      :class="{selected: cardToggler, disabled: disabled}"
      @click="toggleState"
    >
      <div class="card-content">
        <p class="text-16"><span v-html="setHeaderText"></span></p>
        <p class="text-bold text-48">Нямушка</p>
        <p class="text-bold text-24">
          {{ products[product_name]['taste'] }}
        </p>
        <p class="text-14">
          <b>
            <slot name="product_dose">{{ products[product_name]['amount'] }}
</slot>
          </b> порций
          <br>
          <b>
            {{ products[product_name]['surprize'] }}
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
          <slot name="weight"></slot>
        </span>
        <br>
        <span>КГ</span>
      </div>
    </div>
    <div class="card_footer" @click="toggleState"> 
      <span v-html="setFooterText" style="fontSize: 12px"></span>
    </div>
  </div>
</template>

<script>
export default {
  props: ["product_name", "color", "disabled"],
  data: function() {
    return {
      cardToggler: false,
      hover: false,
      products: {
        'fua-gra': {
          'taste':'c фуа-гра',
          'amount': '10',
          'surprize':'мышь',
          'footer': 'Печень утки разварная с артишоками.'
        },
        'fish': {
          'taste':'c рыбой',
          'amount': '40',
          'surprize':'2 мыши',
          'footer': 'Головы щучьи с чесноком да свежайшая сёмгушка.'
        },
        'chicken' : {
          'taste':'c курой',
          'amount': '100',
          'surprize':'5 мышей',
          'footer': 'Филе из цыплят с трюфелями в бульоне.'
        }
      }
    };
  },
  computed: {
    setFooterText: function() {
      
      if (this.disabled) {
        return '<span style="color:#bbbb4b">Печалька, с курой закончился.</span>'
      }
      else if (this.cardToggler==true) {
        return this.products[this.product_name]['footer']
      }
      else  {
        return 'Чего сидишь? Порадуй котэ, <span style="color: #1698d9; border-bottom: 1px dashed"> купи </span>'
      }
    },
    setHeaderText: function() {
      if (this.cardToggler==true && this.hover==false) {
        return '<span style="color: #ee3355">Котэ не одобряет?</span>'
      }
      else {
        return '<span>Сказочное заморское яство</span>'
      }
    }
  },
  methods: {
    toggleState: function() {
      return this.disabled ? this.cardToggler : this.cardToggler=!this.cardToggler
    }
  }
};
</script>

<style scoped>

.card {
  height: 480px;
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

.card_footer {
  color: white;
  text-align: center;
  margin-top: 8px;
}

.selected {
  border: 4px solid #ee3355;
}

.disabled {
  filter: saturate(30%);
  border-color: #767676;
  cursor: default;
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
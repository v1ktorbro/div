<template>
  <article class="slider-hints-container">
    <SliderHints />
    <button class="slider-hints-container__btn-scroll">{{ btnNameScroll }}</button>
  </article>
</template>

<script>
import SliderHints from '../components/SliderHints.vue';
export default {
  name: 'SliderHintsContainer',
  props: {
    btnNameScroll: String,
  },
  components: {
    SliderHints,
  },
};
</script>

<style lang="scss">
$arrowBtnImage: url('../images/icon_middle_arrow.svg');

.slider-hints-container {
  font-family: 'Kinopoisk';
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  z-index: 12;
  top: 200px;
}
.slider-hints-container__btn-scroll {
  background-color: transparent;
  font-family: 'Kinopoisk';
  font-size: 14px;
  line-height: 15px;
  color: #333333;
  border: none;
  cursor: pointer;
  transform: translate(-42%, -460%) rotate(90deg) ;
  &:active {
    scale: 1.03;
    opacity: .5;
  }
  &::after {
    content: $arrowBtnImage;
    position: absolute;
    right: -40px;
    top: -1px;
  }
}
</style>
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
$arrowBtnImage: url('../assets/images/icon_middle_arrow.svg');

.slider-hints-container {
  font-family: 'Kinopoisk';
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  z-index: 12;
  top: 200px;
}
.slider-hints-container__btn-scroll {
  user-select: none;
  background-color: transparent;
  font-family: 'Kinopoisk';
  font-size: 14px;
  line-height: 15px;
  color: #333333;
  border: none;
  cursor: pointer;
  margin-bottom: 70px;
  transform: translate(-42%, -460%) rotate(-90deg) ;
  &:active {
    scale: 1.03;
    opacity: .5;
  }
  &::before {
    content: ' ';
    background-image: $arrowBtnImage;
    background-repeat: no-repeat;
    background-size: 63px 4px;
    background-position: center;
    position: absolute;
    right: 120px;
    top: 3px;
    bottom: 0;
    transform: rotate(180deg);
    width: 63px;
  }
}
</style>
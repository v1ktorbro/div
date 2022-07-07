<template>
  <article class="slider-container">
    <Slider btnName="Искать промокод" />
    <span class="slider-container__emblem">{{ emblem.toLowerCase() }}</span>
  </article>
</template>

<script>
import Slider from '../components/Slider.vue'
export default {
  name: 'SliderContainer',
  props: {
    emblem: String,
  },
  components: {
    Slider,
  },
};
</script>

<style lang="scss">
$cloudsCoverOnPhoto: url('../images/clouds_in_front_picture.png');
$arrowBtnImage: url('../images/icon_middle_arrow.svg');

.slider-container {
  display: flex;
  justify-content: center;
  &::after {
    content: $cloudsCoverOnPhoto;
    position: absolute;
    background-image: $cloudsCoverOnPhoto;
    right: -93%;
    bottom: -64%;
    z-index: 0;
  }
}

  .slider-container__emblem {
    grid-area: emblem;
    font-family: 'Kinopoisk';
    font-size: 14px;
    line-height: 15px;
    position: absolute;
    right: 0;
    top: 50%;
    transform-origin: left;
    transform: translate(50%, -100%) rotate(90deg) ;
    color: #333333;
  }
  
</style>
<template>
  <article class="slider-image-container">
    <SliderImage description="Для примера мы показали вам его лицо.  В первой серии он прячется в подвале 
за мониторами, и пусть борода не собьёт вас с толку. Найдите героя и нажмите  на паузу — 
ему не терпится отдать вам промокод." btnName="Искать промокод" />
    <span class="slider-image-container__emblem">{{ emblem.toLowerCase() }}</span>
  </article>
</template>

<script>
import SliderImage from '../components/SliderImage.vue'
export default {
  name: 'SliderContainer',
  props: {
    emblem: String,
  },
  components: {
    SliderImage,
  },
};
</script>

<style lang="scss">
$cloudsCoverOnPhoto: url('../images/clouds_in_front_picture.png');
$arrowBtnImage: url('../images/icon_middle_arrow.svg');

.slider-image-container {
  display: flex;
  justify-content: center;
  margin-left: 83px;
  &::after {
    content: $cloudsCoverOnPhoto;
    position: absolute;
    background-image: $cloudsCoverOnPhoto;
    right: -44rem;
    bottom: -21rem;
    margin-right: auto;
  }
}
.slider-image-container__emblem {
  font-family: 'Kinopoisk';
  font-size: 14px;
  line-height: 15px;
  position: absolute;
  right: 0;
  top: 40%;
  transform-origin: left;
  transform: translate(50%, -100%) rotate(90deg) ;
  color: #333333;
  z-index: 1;
  user-select: none;
}
</style>
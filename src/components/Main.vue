<template>
  <main class="main">
    <h1 class="main__title">{{ title.toUpperCase() }}</h1>
    <div class="main__wrapper-for-sliders">
      <SliderHintsContainer btnNameScroll="Скрольте вниз" />
      <SliderImageContainer emblem="hd.kinopoisk.ru" />
    </div>
  </main>
</template>

<script>
import SliderImageContainer from './SliderImageContainer.vue';
import SliderHintsContainer from './SliderHintsContainer.vue';

export default {
  name: 'Main',
  props: {
    title: String,
  },
  components: {
    SliderImageContainer,
    SliderHintsContainer,
  },
};
</script>

<style scoped lang="scss">
$textColorTitle: #FFCC64;
$backgroundMainImage: url('../images/background_main.jpg');
$cloudsCoverOnPhoto: url('../images/clouds_in_front_picture.png');
.main {
  font-family: 'Futura';
  background-image: $backgroundMainImage;
  background-size: cover;
  position: relative;
  padding-left: 35px;
  padding-right: 35px;
  padding-top: 20px;
}
.main__wrapper-for-sliders {
  display: flex;
}
.main__title {
  font-size: 45px;
  line-height: 72px;
  font-weight: 700;
  letter-spacing: -0.69px;
  text-align: center;
  color: $textColorTitle;
  margin-top: 50px;
  z-index: 1;
}
</style>
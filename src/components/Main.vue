<template>
  <main class="main">
    <h1 class="main__title">{{ title.toUpperCase() }}</h1>
    <SliderImageContainer emblem="hd.kinopoisk.ru" />
  </main>
</template>

<script>
import SliderImageContainer from './SliderImageContainer.vue';

export default {
  name: 'Main',
  props: {
    title: String,
  },
  components: {
    SliderImageContainer,
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
.main__title {
  font-size: 45px;
  line-height: 72px;
  font-weight: 700;
  letter-spacing: -0.69px;
  text-align: center;
  color: $textColorTitle;
  margin-top: 50px;
}
</style>
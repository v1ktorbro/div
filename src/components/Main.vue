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
$backgroundMainImage: url('../assets/images/background_main.jpg');
$cloudsCoverOnPhoto: url('../assets/images/clouds_in_front_picture.png');
.main {
  font-family: 'Futura';
  background-image: $backgroundMainImage;
  background-size: cover;
  position: relative;
  padding-left: 35px;
  padding-right: 35px;
  z-index: 24;
  padding-top: 20px;
}
.main__wrapper-for-sliders {
  display: grid;
  justify-content: space-between;
  grid-template-columns: minmax(min-content, 117px) minmax(min-content, 902px) minmax(min-content, 50px);
}
.main__title {
  font-size: 45px;
  line-height: 72px;
  font-weight: 700;
  letter-spacing: -0.69px;
  text-align: center;
  color: $textColorTitle;
  margin-top: 50px;
  position: relative;
  z-index: 1;
  padding-top: 24px;
  left: 50%;
  transform: translate(-50%, 0%);
  margin-left: 100px;
}
@media screen and (max-width: 1280px) {
  .main__title {
    margin-left: auto;
    margin-right: auto;
    font-size: 40px;
    line-height: 62px;
  }
}
@media screen and (max-width: 900px) {
  .main__title {
    font-size: 35px;
    line-height: 52px;
  }
}
@media screen and (max-width: 750px) {
  .main__wrapper-for-sliders {
    display: flex;
  }
}
@media screen and (max-width: 650px) {
  .main__title {
    font-size: 30px;
    line-height: 35px;
  }
}
@media screen and (max-width: 550px) {
  .main {
    padding-left: 20px;
    padding-right: 20px;
  }
  .main__title {
    font-size: 26px;
    line-height: 32px;
  }
}
</style>
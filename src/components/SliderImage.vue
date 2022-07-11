<template>
  <aside class="slider-image">
    <span class="slider-image__circle-table-info">{{ `${currentElemOfArrayInfo.cuurentImageNumber} / ${currentElemOfArrayInfo.allElementsInArr}` }}</span>
    <img  :src="require(`../assets/images/${currentElemOfArrayInfo.imageName}`)" alt="Фото знаменитого человека" class="slider-image__image">
    <div class="slider-image__block-description">
    <p class="slider-image__description">{{ currentElemOfArrayInfo.description }}</p>
    <button class="slider-image__btn-pomocode">{{ btnName }}</button>
    </div>
    <button @click="handleChangeImageSlider" type="button" class="slider-image__btn-next" />
  </aside>
</template>

<script>
export default {
  name: 'Slider',
  props: {
    btnName: String,
    handleChangeImageSlider: Function,
    currentElemOfArrayInfo: Object,
  },
  methods: {
    changeSlider() {
      this.handleChangeImageSlider();
    },
  },
};
</script>

<style scoped lang="scss">
$arrowBtnImage: url('../assets/images/icon_short_arrow.svg');
.slider-image {
  font-family: 'Kinopoisk';
  position: relative;
  display: flex;
  flex-direction: column;
}
.slider-image__circle-table-info {
  position: relative;
  width: 56px;
  height: 56px;
  border-radius: 50px;
  font-size: 15px;
  font-weight: 700;
  line-height: 18px;
  display: flex;
  margin: 0 auto 1.3rem;
  align-items: center;
  justify-content: center;
  user-select: none;
  z-index: 3;
  background-color: #fff;
}
.slider-image__block-description {
  z-index: 1;
  display: flex;
  flex-direction: column;
  align-self: center;
  position: absolute;
  bottom: 50px;
}
.slider-image__image {
  width: 303px;
  height: 436px;
  margin: 0 auto;
  user-select: none;
  padding-right: 55px;
}
.slider-image__description {
  text-align: center;
  font-size: 20px;
  line-height: 32px;
  letter-spacing: 0.4px;
  color: #000;
  margin: 0 auto;
  z-index: 1;
}
.slider-image__btn-next {
  z-index: 1;
  border: 1px solid #000;
  border-radius: 50%;
  outline: none;
  width: 40px;
  height: 40px;
  background-color: transparent;
  cursor: pointer;
  position: absolute;
  right: 0;
  top: 35%;
  margin-right: -50px;
  transform: translate(-50%, -50%);
  &:active {
    scale: 1.03;
    opacity: .5;
  }
  &::before {
    content: $arrowBtnImage;
    display: flex;
    object-fit: contain;
    position: absolute;
    left: 50%;
    transform: translate(-50%, -50%);
  }
}
.slider-image__btn-pomocode {
  z-index: 1;
  cursor: pointer;
  background-color: transparent;
  position: relative;
  border: none;
  outline: none;
  color: #333333;
  font-size: 15px;
  line-height: 18px;
  text-align: center;
  display: flex;
  align-self: center;
  user-select: none;
  margin-top: 38px;
  &:active {
    scale: 1.03;
    opacity: .5;
  }
    &::before {
    content: ' ';
    background-image: $arrowBtnImage;
    background-repeat: no-repeat;
    background-size: 30px 4px;
    background-position: center;
    position: absolute;
    right: -60px;
    top: -4px;
    bottom: 0;
    width: 63px;
  }
}

@media screen and (max-width: 1280px) {
  .slider-image__description {
    font-size: 18px;
    line-height: 28px;
  }
}
.slider-image__btn-pomocode {
  margin-top: 30px;
}
@media screen and (max-width: 650px) {
  .slider-image__description  {
    font-size: 16px;
    line-height: 24px;
  }
}
.slider-image__btn-pomocode {
  margin-top: 25px;
}
@media screen and (max-width: 550px) {
  .slider-image__btn-pomocode  {
    margin-top: 15px;
  }
}
@media screen and (max-width: 460px) {
  .slider-image__image {
  width: 263px;
  height: 386px;
}
  .slider-image__btn-next  {
    margin-right: -30px;
  }
}
@media screen and (max-width: 400px) {
  .slider-image__image {
    padding-right: 0px;
  }
}
</style>
<template>
  <aside class="slider-image">
    <span class="slider-image__circle-table-info">1/8</span>
    <img src="../images/main_image_1.png" alt="" class="slider-image__image">
    <div class="slider-image__block-description">
    <p class="slider-image__description">{{ description }}</p>
    <button class="slider-image__btn-pomocode">{{ btnName }}</button>
    </div>
    <button type="button" class="slider-image__btn-next" />
  </aside>
</template>

<script>
export default {
  name: 'Slider',
  props: {
    btnName: String,
    description: String,
  },
};
</script>

<style scoped lang="scss">
$arrowBtnImage: url('../images/icon_short_arrow.svg');
$cloudsCoverOnPhoto: url('../images/clouds_in_front_picture.png');
.slider-image {
  font-family: 'Kinopoisk';
  margin: 0 auto;
  min-width: 902px;
  display: flex;
  flex-direction: column;
  position: relative;
}
.slider-image__circle-table-info {
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
  background-color: #fff;
}
.slider-image__block-description {
  z-index: 1;
  display: flex;
  flex-direction: column;
  align-self: center;
  position: absolute;
  bottom: 40px;
  user-select: none;
}
.slider-image__image {
  width: 303px;
  height: 436px;
  margin: 0 auto;
  padding-right: 55px;
}
.slider-image__description {
  text-align: center;
  font-size: 20px;
  line-height: 32px;
  letter-spacing: 0.4px;
  color: #000;
  margin: 0;
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
  margin-top: 2.4rem;
  &:active {
    scale: 1.03;
    opacity: .5;
  }
  &::after {
    content: $arrowBtnImage;
    position: absolute;
    top: 25%;
    right: -40px;
    transform: translate(0%, -30%);
  }
}
</style>
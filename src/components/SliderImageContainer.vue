<template>
  <article class="slider-image-container">
    <SliderImage :currentElemOfArrayInfo="currentElemOfArrayInfo" :handleChangeImageSlider="handleChangeImageSlider" btnName="Искать промокод" />
    <span class="slider-image-container__emblem">{{ emblem.toLowerCase() }}</span>
  </article>
</template>

<script>
import SliderImage from '../components/SliderImage.vue';
import { initialDb } from '@/assets/initialDb';
export default {
  name: 'SliderContainer',
  data() {
    return {
      currentNumberElemArr: 0,
      currentElemOfArrayInfo: {imageName: '', description: '', cuurentImageNumber: Number, allElementsInArr: Number},
    }
  },
  props: {
    emblem: String,
  },
  components: {
    SliderImage,
  },
  beforeMount: function() {
    this.currentElemOfArrayInfo.imageName = initialDb[this.currentNumberElemArr].imageName;
    this.currentElemOfArrayInfo.description = initialDb[this.currentNumberElemArr].description;
    this.currentElemOfArrayInfo.cuurentImageNumber = this.currentNumberElemArr + 1;
    this.currentElemOfArrayInfo.allElementsInArr = initialDb.length;
  },
  methods: {
    handleChangeImageSlider() {
      this.currentElemOfArrayInfo.cuurentImageNumber  >= this.currentElemOfArrayInfo.allElementsInArr ? this.currentNumberElemArr = 0 : this.currentNumberElemArr++;
      this.currentElemOfArrayInfo = {...this.currentElemOfArrayInfo, imageName: initialDb[this.currentNumberElemArr].imageName, description: initialDb[this.currentNumberElemArr].description, cuurentImageNumber: this.currentNumberElemArr + 1};
    }
  },
};
</script>

<style lang="scss">
$cloudsCoverOnPhoto: url('../assets/images/clouds_in_front_picture.png');
$arrowBtnImage: url('../assets/images/icon_middle_arrow.svg');
.slider-image-container {
  margin-left: 83px;
  &::after {
    content: $cloudsCoverOnPhoto;
    max-width: 100%;
    max-height: 100%;
    position: absolute;
    background-image: $cloudsCoverOnPhoto;
    background-size: cover;
    bottom: 0;
    top: 0;
    left: 0;
    overflow: hidden;
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
  transform: translate(50%, -100%) rotate(90deg);
  color: #333333;
  z-index: 1;
  user-select: none;
}
@media screen and (max-width: 1280px) {
  .slider-image-container {
    margin-right: 50px;
    &::after {
      top: 65px;
    }
  }
}
@media screen and (max-width: 900px) {
  .slider-image-container {
    margin-left: 40px;
  }
}
@media screen and (max-width: 750px) {
  .slider-image-container {
    margin-left: auto;
    margin-right: auto;
  }
}
@media screen and (max-width: 650px) {
  .slider-image-container__emblem {
    right: -30px;
  }
}
@media screen and (max-width: 520px) {
  .slider-image-container__emblem {
    top: 2%;
    font-size: 12px;
    right: -35px;
  }
}
@media screen and (max-width: 400px) {
  .slider-image-container {
    max-width: 280px;
  }
}
</style>
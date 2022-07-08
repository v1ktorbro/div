<template>
  <aside class="slider-hints">
    <ul class="slider-hints__list">
      <li class="slider-hints__item-list"></li>
      <li class="slider-hints__item-list"></li>
      <li class="slider-hints__item-list slider-hints__item-list_active">
        03<span class="slider-hints__active-item-list"> Подсказки</span>
      </li>
      <li class="slider-hints__item-list"></li>
    </ul>
  </aside>
</template>

<script>
export default {
  name: 'SliderHints',
  props: {},
};
</script>

<style lang="scss">
.slider-hints__list {
  padding: 0;
  margin: 0;
  margin-top: 180px;
  color: #333333;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}
.slider-hints__item-list {
  list-style-position: inside;
  list-style-type: '‒';
  margin-bottom: 45px;
  &:first-of-type {
    margin-top: 30px;
  }
  &:last-of-type {
    margin-bottom: 97px;
  }
  &_active {
    border-bottom: 1px solid #333333;
    padding-bottom: 5px;
    list-style-type: none;
    font-size: 16px;
    line-height: 15px;
    font-weight: 500;
    user-select: none;
  }

}

.slider-hints__active-item-list {
  margin-left: 20px;
  font-size: 14px;
  font-weight: 400;

}
</style>
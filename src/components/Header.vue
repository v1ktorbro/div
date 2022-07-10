<template>
<header class="header">
  <button @click="handlerBtnMenu" type="button" class="header__btn-menu" />
  <a href="https://www.kinopoisk.ru/" target="_blank" class="header__logo" />
</header>
</template>

<script>
export default {
  name: 'Header',
  methods: {
    handlerBtnMenu() {
      alert('Яб тоже хотел что-бы по клику что-то происходило, но увы, в другой раз!')
    }
  },
};
</script>

<style scoped lang="scss">
$btnMenu: url('../assets/images/icon_menu.svg');
$logo: url('../assets/images/logo.svg');

.header {
  display: grid;
  grid-template-areas: 'btn-menu logo .';
  justify-content: space-between;
  align-items: center;
  position: absolute;
  top: 40px;
  width: calc(100% - 70px);
  z-index: 30;
  margin-left: 35px;
  margin-right: 35px;
}

.header__btn-menu {
  border: none;
  outline: none;
  background-image: $btnMenu;
  background-repeat: no-repeat;
  width: 20px;
  height: 16px;
  background-size: 20px 16px;
  cursor: pointer;
  background-color: transparent;
}

.header__logo {
  background-image: $logo;
  width: 183px;
  height: 25px;
  background-repeat: no-repeat;
  margin-left: 100px;
}

</style>
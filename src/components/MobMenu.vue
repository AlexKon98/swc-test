<template>
  <div class="mob-menu" ref="menu">
    <button @click="changeShow" class="mob-menu__close">
      <div class="top"></div>
      <div class="bottom"></div>
    </button>
    <ul class="mob-menu__list">
      <li class="mob-menu__item">
        <router-link to="/">Преимущества</router-link>
      </li>
      <li class="mob-menu__item">
        <router-link to="/">Услуги</router-link>
      </li>
      <li class="mob-menu__item">
        <router-link to="/">Виджет</router-link>
      </li>
      <li class="mob-menu__item">
        <router-link to="/">Кому</router-link>
      </li>
      <li class="mob-menu__item">
        <router-link to="/">Тарифы</router-link>
      </li>
      <li class="mob-menu__item">
        <router-link to="/">Блог</router-link>
      </li>
    </ul>
    <router-link class="mob-menu__change-lang" to="/">En</router-link>
    <a class="mob-menu__tel" href="tel:+74951234567">
      <img src="@/assets/icons/phone.svg" alt="">
    </a>
  </div>
</template>

<script>
export default {
  name: 'MobMenu',
  props: {
    show: {
      type: Boolean
    }
  },
  methods: {
    changeShow() {
      this.$refs.menu.style.transform = 'translate(-100%)';
      setTimeout(() => {
        this.$emit('changeShow', false);
      }, 300);
    }
  },
  mounted() {
    setTimeout(() => {
      this.$refs.menu.style.transform = 'translate(0)';
    }, 100);
  }
}
</script>

<style lang="scss" scoped>
.mob-menu {
  position: fixed;
  left: 0;
  top: 0;
  bottom: 0;
  z-index: 2;
  background-color: #49a1f1;
  padding: 40px 60px;
  transform: translate(-100%);
  transition: transform .3s linear;
  box-shadow: 2px 0 2px #49a1f1;
  &__tel {
    display: none;
  }
  &__list {
    display: flex;
    flex-direction: column;
    gap: 25px 0;
    margin: 60px 0;
  }
  &__item a {
    color: #08123A;
    font-family: 'Text';
    font-size: 16px;
    font-style: normal;
    font-weight: 500;
    line-height: 20px;
    transition: color .3s linear;
    &:hover {
      color: #fff;
    }
  }
  &__change-lang {
    color: #fff;
    font-family: 'Text';
    font-size: 16px;
    font-style: normal;
    font-weight: 500;
    line-height: 20px;
    transition: color .3s linear;
    &:hover {
      color: rgba(255, 255, 255, .75);
    }
  }
  &__close {
    display: block;
    position: absolute;
    top: 10px;
    left: 10px;
    border: none;
    background-color: transparent;
    cursor: pointer;
    width: 30px;
    height: 30px;
    overflow: hidden;
    margin-bottom: 35px;
    div {
      height: 3px;
      position: absolute;
      left: 0;
      right: 0;
      background-color: #fff;
      border-radius: 2px;
    }
    .top {
      top: 2px;
      transform: rotate(45deg) translate(10px, 10px);
    }
    .bottom {
      bottom: 2px;
      transform: rotate(-45deg) translate(6px, -6px);
    }
  }
}

@media (max-width: 768px) {
  .mob-menu {
    right: 0;
    padding: 40px 15px;
    &__list {
      margin: 10px 0;
      gap: 15px 0;
    }

    &__change-lang {
      display: block;
      margin-top: 20px;
    }

    &__tel {
      display: block;
      position: absolute;
      bottom: 15px;
      right: 15px;
      img {
        width: 30px;
        height: 30px;

      }
    };
  }
}
</style>
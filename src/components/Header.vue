<template>
  <header class="header">
    <div class="container">
      <router-link class="header__logo" to="/">
        <img src="@/assets/icons/logo.svg" alt="">
      </router-link>
      <nav class="header__nav">
        <ul class="header__list">
          <li class="header__item">
            <router-link to="/">Преимущества</router-link>
          </li>
          <li class="header__item">
            <router-link to="/">Услуги</router-link>
          </li>
          <li class="header__item">
            <router-link to="/">Виджет</router-link>
          </li>
          <li class="header__item">
            <router-link to="/">Кому</router-link>
          </li>
          <li class="header__item">
            <router-link to="/">Тарифы</router-link>
          </li>
          <li class="header__item">
            <router-link to="/">Блог</router-link>
          </li>
        </ul>
      </nav>
      <router-link class="header__change-lang" to="/">En</router-link>
      <div class="header__contacts">
        <a class="header__tel" href="tel:+74951234567">+7 (495) 123-45-67</a>
        <button class="header__open-popup blue-btn">
          Контакты
        </button>
      </div>
      <button @click="changeShow" class="header__menu" :class="{'active' : show}">
        <div class="top"></div>
        <div class="mid"></div>
        <div class="bottom"></div>
      </button>
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header',
  props: {
    show: {
      type: Boolean
    }
  },
  methods: {
    changeShow() {
      this.$emit('changeShow', !this.show);
    }
  },
}
</script>

<style lang="scss" scoped>
.header {
  padding: 32px 0;
  position: relative;
  z-index: 1;
  &__menu {
    display: none;
  }
  &__logo {
    margin-right: auto;
  }
  &__nav {
    margin-left: 35px;
    margin-right: 73px;
  }
  &__change-lang {
    margin-right: 78px;
  }
  &__item a {
    display: block;
    color: #5F6B77;
    font-family: 'Text';
    font-size: 16px;
    font-style: normal;
    font-weight: 500;
    line-height: 20px;
    position: relative;
    overflow: hidden;
    &::after {
      content: '';
      position: absolute;
      background-color: #5F6B77;
      bottom: 0;
      left: 0;
      right: 0;
      height: 1px;
      transform: translateX(-100%);
      transition: transform .3s linear;
    }
    &:hover::after {
      transform: translateX(0);
    }
  }
  &__change-lang {
    color: #8B9FCC;
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
  &__tel {
    color: #FFF;
    font-family: 'Inter';
    font-size: 16px;
    font-style: normal;
    font-weight: 600;
    line-height: 22px;
    transition: opacity .3s linear;
    &:hover {
      opacity: .65;
    }
  }
  &__open-popup {
    padding: 12px 24px;
  }
}

.header__contacts,
.header__list,
.container {
  display: flex;
  align-items: center;
}

.container {
  padding-left: 134px;
}

.header__contacts {
  gap: 0 15px;
}

.header__list {
  gap: 0 35px;
}

@media (max-width: 1270px) {
  .header__nav, .header__change-lang {
    display: none;
  }
  .header__menu {
    display: block;
    position: relative;
    border: none;
    background-color: transparent;
    cursor: pointer;
    width: 30px;
    height: 30px;
    overflow: hidden;
    margin-left: 35px;
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
      transition: transform .3s linear;
    }
    .mid {
      top: calc(50% - 1px);
      transition: opacity .3s linear;
    }
    .bottom {
      bottom: 2px;
      transition: transform .3s linear;
    }
    &.active {
      .mid {
        opacity: 0;
      }
      .top {
        transform: rotate(45deg) translate(10px, 10px);
      }
      .bottom {
        transform: rotate(-45deg) translate(6px, -6px);
      }
    }
  }
}
</style>
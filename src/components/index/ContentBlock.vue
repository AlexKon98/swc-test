<template>
  <div class="container">
    <h1 class="content__title">
      Техническая поддержка сайтов, CRM систем и мобильных приложений
    </h1>
    <div class="content__text">
      Профессиональное техническое сопровождение и обслуживание сайтов: полный комплекс услуг от опытных экспертов
    </div>
    <router-link class="content__btn dark-blue-btn" to="/">Подключиться</router-link>
    <button class="content__scroll">
      <img src="@/assets/icons/arrow.svg" alt="">
    </button>
  </div>
</template>

<script>
export default {
  name: 'ContentBlock',
}
</script>

<style lang="scss" scoped>
.container {
  padding-left: 134px;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.content__title {
  max-width: 570px;
  margin-bottom: 41px;
  color: #08123A;
  font-family: 'Display';
  font-size: 48px;
  font-style: normal;
  font-weight: 600;
  line-height: 58px;
}

.content__text {
  max-width: 560px;
  color: #5F6B77;
  font-family: 'Inter';
  font-size: 20px;
  font-style: normal;
  font-weight: 400;
  line-height: 28px;
  margin-bottom: 41px;
}

.content__btn {
  display: block;
  margin-bottom: 43px;
  padding: 15px 14px;
}

.content__scroll {
  display: block;
  position: relative;
  padding: 20px;
  background-color: transparent;
  border-radius: 8px;
  border: 1px solid #E9EAF0;
  cursor: pointer;
  overflow: hidden;
  img {
    position: relative;
    z-index: 1;
  }
  &::after {
    content: '';
    position: absolute;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    background-color: #E9EAF0;;
    transform: translateY(100%);
    transition: transform .3s linear;
    z-index: 0;
  }
  &:hover::after {
    transform: translate(0);
  }
}

@media (max-width: 1270px) {
  .container {
    padding: 0 40px;
  }
}

@media (max-width: 999px) {
  .content__text {
    text-shadow: .5px .5px 1px #DFE8F4;
  }
}

@media (max-width: 768px) {
  .content__text {
    text-shadow: none;
  }

  .content__title {
    font-size: 30px;
    line-height: 36px;
  }

  .content__title, .content__text {
    max-width: none;
  }

  .content__btn,
  .content__text,
  .content__title {
    margin-bottom: 20px;
  }

  .container {
    padding: 0 20px;
  }
}
</style>
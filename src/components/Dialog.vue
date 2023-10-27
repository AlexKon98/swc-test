<template>
  <div class="dialog" v-if="open" @click.capture="closeDialog">
    <div class="dialog__contacts">
      <h2 class="dialog__title">Контактная информация</h2>
      <div class="dialog__geo">
        <div class="dialog__office gray-heading">
          <img src="@/assets/icons/pin.svg" alt="">
          <span>Наш офис</span>
        </div>
        <div class="dialog__address">Санкт-Петербург, ул. Такая-то, д. 1</div>
        <button class="dialog__show-map">Показать на карте</button>
      </div>
      <div class="dialog__contact">
        <dl>
          <div>
            <dt>Звоните:</dt>
            <dd>
              <a href="tel:+74951234567">+7 (495) 123-45-67</a>
            </dd>
          </div>
          <div>
            <dt>Пишите:</dt>
            <dd>
              <a href="mailto:info@test.ru">info@test.ru</a>
            </dd>
          </div>
        </dl>
        <button class="dialog__btn white-btn">
          Заказать звонок
        </button>
      </div>
      <div class="dialog__time">
        <div class="dialog__time-title gray-heading">
          <img src="@/assets/icons/clock.svg" alt="">
          <span>Режим работы</span>
        </div>
        <div class="dialog__work-days">
          <div>Пн-Пт — с 10:00 до 18:00</div>
          <div>Сб-Вс — выходной</div>
        </div>
      </div>
      <div class="dialog__social">
        <div class="dialog__social-title gray-heading">
          <span>Мы в соцсетях</span>
        </div>
        <ul class="dialog__socila-list">
          <li class="border">
            <a href="#">
              <img src="@/assets/icons/tg.svg" alt="">
            </a>
          </li>
          <li class="border">
            <a href="#">
              <img src="@/assets/icons/vk.svg" alt="">
            </a>
          </li>
          <li class="">
            <a href="#">
              <img src="@/assets/icons/yzen.svg" alt="">
            </a>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Dialog',
  props: {
    open: {
      type: Boolean
    }
  },
  methods: {
    closeDialog(evt) {
      if (evt.target === evt.currentTarget) this.$emit('closeDialog', false);
    }
  }
}
</script>

<style lang="scss" scoped>
.gray-heading {
  align-items: center;
  color: #5F6B77;
  font-family: 'Inter';
  font-size: 16px;
  font-style: normal;
  font-weight: 600;
  line-height: 20px;
  span {
    padding-left: 5px;
  }
}

.dialog {
  padding: 10px;
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 3;
  background-color: rgba(0, 0, 0, .5);
  display: flex;
  align-items: center;
  justify-content: center;
  &__contacts {
    padding: 38px;
    border-radius: 11px;
    background-color: #FFF;
  }
  &__title {
    color: #08123A;
    font-family: 'Inter';
    text-align: center;
    font-size: 20px;
    font-style: normal;
    font-weight: 600;
    line-height: 22px;
    margin-bottom: 30px;
  }
  &__office, &__time-title {
    display: flex;
    margin-bottom: 13px;
    margin-left: -3px;
  }
  &__address {
    color: #000;
    font-family: 'Inter';
    font-size: 16px;
    font-style: normal;
    font-weight: 600;
    line-height: 20px;
    margin-bottom: 10px;
  }
  &__show-map {
    color: #506CCF;
    font-family: 'Inter';
    font-size: 16px;
    font-style: normal;
    font-weight: 600;
    line-height: 18px;
    cursor: pointer;
    background-color: transparent;
    border: none;
    border-bottom: 1px solid #506CCF;
    margin-bottom: 30px;
  }
  &__btn {
    padding: 16px 25px;
  }
  &__contact {
    display: flex;
    align-items: center;
    margin-bottom: 30px;
    dl {
      display: flex;
      flex-direction: column;
      gap: 10px 0;
      margin-right: 60px;
      div {
        display: flex;
      }
      dt {
        color: #5F6B77;
        font-family: 'Inter';
        font-size: 16px;
        font-style: normal;
        font-weight: 600;
        line-height: 20px;
      }
      dd a {
        color: #08123A;
        font-family: 'Inter';
        font-size: 16px;
        font-style: normal;
        font-weight: 600;
        line-height: 20px;
        padding-left: 8px;
      }
    }
  }
  &__time {
    margin-bottom: 20px;
  }
  &__work-days {
    display: flex;
    flex-direction: column;
    gap: 5px 0;
    color: #08123A;
    font-family: 'Inter';
    font-size: 16px;
    font-style: normal;
    font-weight: 600;
    line-height: 20px;
  }
  &__social-title {
    margin-bottom: 12px;
    span {
      padding-left: 0;
    }
  }
  &__socila-list {
    display: flex;
    align-items: stretch;
    gap: 0 18px;
    li {
      display: flex;
      justify-content: center;
      align-items: center;
      width: 40px;
      height: 40px;
    }
    .border {
      border-radius: 10px;
      border: 2px solid #E9EAF0;
    }
  }
}

@media (max-width: 999px) {
  .dialog {
    align-items: flex-start;
    overflow: auto;
  }

  .dialog__contact {
    flex-direction: column;
    align-items: unset;
    dl {
      margin-right: 0;
      margin-bottom: 10px;
    }
  }
}
</style>
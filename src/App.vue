<template>
  <div>
    <Header @changeShow="changeShow" :show="show" />
    <router-view/>
    <div class="main-bg"></div>
    <MobMenu
      v-if="show"
      @changeShow="changeShow"
      :show="show"
    />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import MobMenu from './components/MobMenu.vue';

export default {
  name: 'App',
  data() {
    return {
      show: false
    }
  },
  methods: {
    changeShow(val) {
      this.show = val;
    }
  },
  components: {
    Header,
    MobMenu
  }
}
</script>

<style lang="scss">
@import url(./assets/style.scss);

.container {
  display: block;
  max-width: 1920px;
  padding: 0 40px;
  margin: 0 auto;
}

.main {
  position: relative;
  z-index: 1;
  &-bg {
    position: fixed;
    top: 0;
    right: 0;
    bottom: 0;
    width: 458px;
    z-index: 0;
    background: var(--gradient-purple, linear-gradient(45deg, #506CCF 0%, #3453C2 100%));
  }
}

.blue-btn {
  background-color: #49a1f1;
  color: #FFF;
  font-family: 'Inter';
  font-size: 16px;
  font-style: normal;
  font-weight: 600;
  line-height: 22px;
  border-radius: 10px;
  border: none;
  cursor: pointer;
  transition: background-color .3s linear;
  &:hover {
    background-color: rgba(73, 161, 241, .75);
  }
}

.dark-blue-btn {
  border-radius: 10px;
  background-color: #506CCF;
  box-shadow: 0px 20px 35px 0px #DFE8F4;
  border: none;
  cursor: pointer;
  color: #FFF;
  font-family: 'Text';
  font-size: 16px;
  font-style: normal;
  font-weight: 500;
  line-height: 22px;
  transition: background-color .3s linear;
  &:hover {
    background-color: rgba(80, 108, 207, .75);
  }
}
</style>

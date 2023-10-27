<template>
  <div>
    <Header
      @openDialog="showDialog"
      @changeShow="changeShowHead"
      :show="show"
    />
    <router-view/>
    <div class="main-bg">
      <GraphBlock />
    </div>
    <MobMenu
      v-if="show"
      @changeShow="changeShow"
      :show="show"
      ref="mob"
    />
    <Dialog
      v-if="open"
      :open="open"
      @changeView="showDialog"
      @closeDialog="showDialog"
    />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import MobMenu from './components/MobMenu.vue';
import GraphBlock from './components/index/GraphBlock.vue';
import Dialog from './components/Dialog.vue';

export default {
  name: 'App',
  data() {
    return {
      show: false,
      open: false,
    }
  },
  watch: {
    open(val) {
      if (val) document.querySelector('body').style.overflow = 'hidden';
      else document.querySelector('body').style = null;
    }
  },
  methods: {
    changeShow(val) {
      this.show = val;
    },
    changeShowHead(val) {
      if (val === true) this.show = val;
      else {
        this.$refs.mob.$refs.menu.style.transform = 'translate(-100%)';
        setTimeout(() => {
          this.show = val;
        }, 300);
      }
    },
    showDialog(val) {
      this.open = val;
    }
  },
  components: {
    Header,
    MobMenu,
    GraphBlock,
    Dialog
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
    position: absolute;
    top: 0;
    right: 0;
    min-width: 458px;
    min-height: 800px;
    width: 30vw;
    height: 100vh;
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

.white-btn {
  color: #5F6B77;
  font-family: 'Inter';
  font-size: 16px;
  font-style: normal;
  font-weight: 600;
  line-height: 20px;
  background-color: transparent;
  border: 2px solid #5F6B77;
  border-radius: 10px;
  transition: background-color .3s linear, color .3s linear;
  &:hover {
    color: #fff;
    background-color: #5F6B77;
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

@media (min-width: 1670px) {
  .main-bg {
    width: 25vw;
  }
}

@media (max-width: 768px) {
  .main-bg {
    display: none;
  }
}
</style>

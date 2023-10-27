<template>
  <main class="main">
    <section class="content">
      <ContentBlock/>
    </section>
  </main>
</template>

<script>
import ContentBlock from '../components/index/ContentBlock.vue'

export default {
  name: 'IndexPage',
  components: {
    ContentBlock
  }
}
</script>

<style lang="scss" scoped>
.content {
  margin-top: 132px;
}

@media (max-width: 768px) {
  .content {
    margin-top: 20px;
  }
}
</style>
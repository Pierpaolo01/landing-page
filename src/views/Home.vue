<template>
  <div class="home">
    <TheHeader />

    <Introduction />
  </div>
</template>

<script>
import TheHeader from '../components/TheHeader.vue';
import Introduction from '../components/Introduction.vue';

export default {
  name: 'Home',
  components: {
    TheHeader,
    Introduction,
  }
}
</script>
<style lang="scss" scoped>
.home{
  height: 100%;
  width: 100%;
}
</style>
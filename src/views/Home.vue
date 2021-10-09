<template>
  <div class="home">
    <TheHeader />
  </div>
</template>

<script>
import TheHeader from '../components/TheHeader.vue';
export default {
  name: 'Home',
  components: {
    TheHeader,
  }
}
</script>
<style lang="scss" scoped>
.home{
  height: 100%;
  width: 100%;
}
</style>
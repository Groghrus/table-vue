<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
import Header from '@/components/common/Header';
import Footer from '@/components/common/Footer';

export default {
    components: {Footer, Header},
};
</script>

<style lang="scss">
@import "@/assets/scss/main.scss";

#app {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}
</style>

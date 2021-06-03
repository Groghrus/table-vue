<template>
  <div class="header">
    <div class="header-top">
      <div class="container"></div>
    </div>
    <div class="header-bottom">
      <div class="container"></div>
    </div>
  </div>
</template>

<script>

export default {
    name: 'Header',
    components: {},
    props: {},
    data() {
        return {

        };
    },
    computed: {
    },
    methods: {
    },
};
</script>

<style lang="scss" scoped>
@import "@/assets/scss/main.scss";

.header {
  border: 2px solid black;
  &-top {
    height: 53px;
    background-color: $primary-color;
  }
  &-bottom {
    height: 85px;
    background-color: $bg-color;
  }
}

</style>

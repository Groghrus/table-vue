<template>
  <input class="inpt form-border" type="text" name="input" value="Input Name">
</template>

<script>
export default {
  name: "vInput",
  props: {},
  data() {
    return {}
  },
  computed: {}
}
</script>

<style lang="scss" scoped>
@import "@/assets/scss/main.scss";
.inpt {
  width: 300px;
  height: 50px;
  padding: 16px 15px;
  font-size: 14px;
  font-weight: 400;
  line-height: 17.5px;
  color: $form-lbl-color;
  &:focus {
    color: $form-lbl-color;
  }
  @include media-breakpoint-down(sm) {
    width: 235px;
  }
}
</style>
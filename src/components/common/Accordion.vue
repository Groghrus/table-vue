<template>
  <div class="accordion">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "Accordion",
  props: {
    title: {
      type: String,
      default: 'accordion title'
    }
  },
  data() {
    return {}
  },
  provide() {
    return { Accordion: this.Accordion }
  }
}
</script>

<style lang="scss">
@import "@/assets/scss/main.scss";
.accordion {
  background: $bg-color;
  border: 1px solid $border-gray;
  box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.05);
  border-radius: 10px;
  margin-bottom: 10px;
}
</style>
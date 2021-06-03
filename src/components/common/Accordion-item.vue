<template>
  <div class="accordion-item">
    <div
        class="accordion-item__header"
        @click="openAccordion"
    >
      <slot name="accordion__header"></slot>
      <svg
          :class="{ rotate: isOpen }"
          class="accordion-item__icon"
          width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path
            d="M13.168 10.4648C13.332 10.3555 13.3867 10.1914 13.3867 10C13.3867 9.83594 13.332 9.67187 13.168 9.53516L7.86328 4.23047C7.75391 4.12109 7.58984 4.03906 7.39844 4.03906C7.23437 4.03906 7.07031 4.12109 6.93359 4.23047L6.33203 4.83203C6.22266 4.96875 6.14062 5.13281 6.14062 5.29687C6.14062 5.48828 6.19531 5.65234 6.30469 5.76172L10.543 10L6.30469 14.2383C6.19531 14.375 6.14062 14.5391 6.14062 14.7031C6.14062 14.8945 6.22266 15.0586 6.33203 15.168L6.93359 15.7695C7.07031 15.9062 7.23437 15.9609 7.39844 15.9609C7.58984 15.9609 7.75391 15.9062 7.86328 15.7695L13.168 10.4648Z"
            fill="#97A8BE"/>
      </svg>

    </div>
    <div
        class="accordion-item__content"
        v-show="isOpen"
    >
      <slot name="accordion__content"></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "Accordion-item",
  props: {},
  inject: ["Accordion"],
  data() {
    return {
      isOpen: false
    }
  },
  methods: {
    openAccordion() {
      this.isOpen = !this.isOpen
    },
    start(el) {
      el.style.height = el.scrollHeight + "px";
    },
    end(el) {
      el.style.height = "";
    }
  }
}
</script>

<style lang="scss">
@import "@/assets/scss/main.scss";

.accordion-item {

  &__header {
    padding: 10px 20px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    cursor: pointer;
  }

  &__icon {
    transition-duration: 0.3s;
  }

  &__icon.rotate {
    transform: rotate(90deg);
    transition-duration: 0.3s;
  }

  &__content {
    padding: 10px 20px 56px 20px;
    animation: flipdown 0.5s ease both;
  }
}


</style>
<template>
  <div class="table-mobile">
    <div class="table-mobile__card form-border" v-for="(item, index) in items" :key="index">
      <div class="flex table-mobile__top">
        <svg class="table-icon" width="32" height="32" viewBox="0 0 32 32" fill="none"
             xmlns="http://www.w3.org/2000/svg">
          <circle cx="16" cy="16" r="16" fill="#F5FAFF"/>
          <path
              d="M19 15.75C19 15.6562 18.9375 15.5625 18.875 15.5C18.8125 15.4375 18.7188 15.375 18.625 15.375H13.375C13.25 15.375 13.1562 15.4375 13.0938 15.5C13.0312 15.5625 13 15.6562 13 15.75V16.625C13 16.75 13.0312 16.8438 13.0938 16.9062C13.1562 16.9688 13.25 17 13.375 17H18.625C18.7188 17 18.8125 16.9688 18.875 16.9062C18.9375 16.8438 19 16.75 19 16.625V15.75ZM18.625 18C18.7188 18 18.8125 18.0625 18.875 18.125C18.9375 18.1875 19 18.2812 19 18.375V19.25C19 19.375 18.9375 19.4688 18.875 19.5312C18.8125 19.5938 18.7188 19.625 18.625 19.625H13.375C13.25 19.625 13.1562 19.5938 13.0938 19.5312C13.0312 19.4688 13 19.375 13 19.25V18.375C13 18.2812 13.0312 18.1875 13.0938 18.125C13.1562 18.0625 13.25 18 13.375 18H18.625ZM22 12.125C22 11.7188 21.8438 11.375 21.5625 11.0625L18.9375 8.4375C18.625 8.15625 18.2812 8 17.875 8H11.5C11.0625 8 10.7188 8.15625 10.4375 8.4375C10.125 8.75 10 9.09375 10 9.5V22.5C10 22.9375 10.125 23.2812 10.4375 23.5625C10.7188 23.875 11.0625 24 11.5 24H20.5C20.9062 24 21.25 23.875 21.5625 23.5625C21.8438 23.2812 22 22.9375 22 22.5V12.125ZM18 9.625L20.375 12H18V9.625ZM20.5 22.5H11.5V9.5H16.5V12.75C16.5 12.9688 16.5625 13.1562 16.7188 13.2812C16.8438 13.4375 17.0312 13.5 17.25 13.5H20.5V22.5Z"
              fill="#409EFF"/>
        </svg>
        <div>
          <p class="table-title">{{ item.title }}</p>
          <p class="table-name">{{ item.name }}</p>
          <p class="table-comment">{{ item.comment }}</p>
        </div>
      </div>

      <div class="flex table-mobile__bottom">
        <div class="table-date table-date__mobile">{{ item.date }}</div>
        <div class="table-status table-status__mobile flex-start">
          <div class="circle" :class="item.statusColor"></div>
          <div>{{ item.status }}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "vTableMobile",
  props: {
    items: {
      type: Array,
      default: () => {
        return []
      }
    },
    statusColor: {
      type: String,
      default: 'green'
    }
  },
  data() {
    return {}
  },
  computed: {}
}
</script>

<style lang="scss">
@import "@/assets/scss/main.scss";

.table-mobile {
  display: none;
  margin-top: 14px;

  @include media-breakpoint-down(sm) {
    display: block;
  }

  &__card {
    margin-bottom: 5px;
  }

  &__top {
    align-items: flex-start !important;
    justify-content: flex-start !important;
    border-bottom: 1px solid $border-gray;
    padding: 10px 8px;
  }

  &__bottom {
    justify-content: flex-start !important;
    padding: 8px 10px;
  }
  .table-date__mobile {
    margin-left: 42px;
  }
  .table-status__mobile {
    margin-left: 60px;
  }
}
</style>
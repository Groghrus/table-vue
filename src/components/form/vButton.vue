<template>
  <button
      class="btn flex"
      :class="className"
      @click="click"
  >
    <svg
        v-if="showIcon"
        width="25" height="24" viewBox="0 0 25 24" fill="none" xmlns="http://www.w3.org/2000/svg">
      <path
          d="M10.2578 16.7539C10.3672 16.918 10.5312 16.9727 10.75 16.9727C10.9414 16.9727 11.1055 16.918 11.2422 16.7539L19.3086 8.71484C19.418 8.60547 19.5 8.44141 19.5 8.22266C19.5 8.03125 19.418 7.86719 19.3086 7.73047L18.2969 6.74609C18.1602 6.60938 17.9961 6.52734 17.8047 6.52734C17.6133 6.52734 17.4492 6.60938 17.3125 6.74609L10.75 13.3086L7.6875 10.2461C7.52344 10.1094 7.35938 10.0273 7.16797 10.0273C6.97656 10.0273 6.8125 10.1094 6.70312 10.2461L5.69141 11.2305C5.55469 11.3672 5.5 11.5312 5.5 11.7227C5.5 11.9414 5.55469 12.1055 5.69141 12.2148L10.2578 16.7539Z"
          fill="white"/>
    </svg>
    <span>{{title}}</span>
  </button>
</template>

<script>
export default {
  name: "vButton",
  props: {
    title: {
      type: String,
      default: 'Отмена'
    },
    fullBackground: {
      type: Boolean,
      default: false
    },
    showIcon: {
      type: Boolean,
      default: false
    },
    bigBtn: {
      type: Boolean,
      default: false
    }
  },
  data() {
    return {
    }
  },
  computed: {
    className() {
      return {
        'btn__full-bg': this.fullBackground,
        'btn__big': this.bigBtn
      }
    }
  },
  methods: {
    click() {
      this.$emit('click')
    }
  }
}
</script>

<style lang="scss" scoped>
@import "@/assets/scss/main.scss";
.btn {
  background-color: $bg-color;
  border: 1px solid $btn-color;
  width: 85px;
  height: 40px;
  font-weight: 400;
  font-size: 16px;
  line-height: 20px;
  color: $btn-color;
  border-radius: 3px;
  &__full-bg {
    background-color: $btn-color-no;
    color: $bg-color;
    border: none;
    &:hover {
      background: $btn-color;
    }
  }
  &__big {
    width: 140px;
  }
}

</style>
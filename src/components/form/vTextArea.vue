<template>
  <div class="txtarea flex flex-col-start">
    <label class="txtarea-lbl" for="txta">Comment</label>
    <textarea
        id="txta"
        class="form-border txtarea-txt"
        name="textarea"
        placeholder="Sample Text Comment"
        required
    ></textarea>
  </div>
</template>

<script>
export default {
  name: "vTextArea",
  props: {
  },
  data() {
    return {}
  },
  computed: {}
}
</script>

<style lang="scss" scoped>
@import "@/assets/scss/main.scss";
textarea {
  &::placeholder {
    font-size: 16px;
    font-weight: 400;
    line-height: 20px;
    color: $form-text-color;
  }
  &:invalid {
    border: 1px solid $canceled;
  }
}
.txtarea {
  position: relative;
  &-txt {
    width: 400px;
    height: 120px;
    resize: none;
    padding: 25px 15px;
    @include media-breakpoint-down(sm) {
      width: 235px;
    }
  }
  &-lbl {
    position: absolute;
    top: 6px;
    left: 15px;
    font-size: 11px;
    font-weight: 400;
    line-height: 13.8px;
    color: $form-lbl-color;
  }

}

</style>
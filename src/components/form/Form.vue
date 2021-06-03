<template>
  <form class="form">
    <div><v-input/></div>
    <div class="flex-start">
      <v-input-date/>
      <svg class="form-line" width="9" height="2" viewBox="0 0 9 2" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M8.67188 1.18555H0.84375V0.300781H8.67188V1.18555Z" fill="#B1C2DA"/>
      </svg>
      <v-input-date />
    </div>
    <div class="flex-col-start flex">
      <v-text-area/>
      <v-text-area/>
    </div>
    <div class="flex-start">
      <v-button
          title="Отправить"
          :full-background="true"
          :show-icon="true"
          :big-btn="true"
          class="form-btn"
          @click="sendData"
      />
      <v-button
          :show-icon="false"
          @click="closeForm"
      />
    </div>
  </form>
</template>

<script>
import VButton from "@/components/form/vButton";
import VTextArea from "@/components/form/vTextArea";
import VInput from "@/components/form/vInput";
import VInputDate from "@/components/form/vInputDate";

export default {
  name: "Form",
  components: {VInputDate, VInput, VTextArea, VButton},
  props: {},
  data() {
    return {}
  },
  methods: {
    sendData() {
      console.log('Send data to server...')
    },
    closeForm() {
      console.log('Close form.')
    }
  }
}
</script>

<style lang="scss" scoped>
@import "@/assets/scss/main.scss";

.form {
  @include media-breakpoint-down(sm) {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  div {
    margin-bottom: 15px;
    &:nth-child(4) {
      margin-bottom: 25px;
    }
  }
  &-btn {
    margin-right: 10px;
  }
  &-line {
    margin: 0 5px 13px 5px;
  }
}

</style>
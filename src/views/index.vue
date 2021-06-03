<template>
  <main class="main">
    <div class="head-page container">
      <Accordion>
        <AccordionItem>
          <template slot="accordion__header">
            <h2>General Information</h2>
          </template>
          <template slot="accordion__content">
            <GeneralTable/>
          </template>
        </AccordionItem>
      </Accordion>
      <Accordion>
        <AccordionItem>
          <template slot="accordion__header">
            <h2>Title Form</h2>
          </template>
          <template slot="accordion__content">
            <Form/>
          </template>
        </AccordionItem>
      </Accordion>
    </div>
  </main>
</template>

<script>

import Accordion from "@/components/common/Accordion";
import AccordionItem from "@/components/common/Accordion-item";
import Form from "@/components/form/Form";
import GeneralTable from "@/components/table/GeneralTable";
export default {
    name: 'Index',
    components: {
      GeneralTable,
      Form,
      AccordionItem,
      Accordion
    },
    props: {
    },
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

<style lang="scss">
@import "@/assets/scss/main.scss";
.head-page {
  height: 100vh;
  width: 100%;
}
</style>

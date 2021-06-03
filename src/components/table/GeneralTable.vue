<template>
  <div class="tabs">
    <ul class="tabs-nav flex-start">
      <li
          class="tabs-nav__item"
      >
        <a
            @click.prevent="setActive('tab1')"
            :class="{ active: isActive('tab1') }"
            href="#tab1" class="tabs-nav__link">Tab Number 1</a>
      </li>
      <li
          class="tabs-nav__item"
      >
        <a
            @click.prevent="setActive('tab2')"
            :class="{ active: isActive('tab2') }"
            href="#tab2" class="tabs-nav__link">Tab Number 2</a>
      </li>
      <li
          class="tabs-nav__item"
      >
        <a
            @click.prevent="setActive('tab3')"
            :class="{ active: isActive('tab3') }"
            href="#tab3" class="tabs-nav__link">Tab Number 3</a>
      </li>
    </ul>
    <hr color="#DFE4ED" size="2px">
    <div class="tabs-content">
      <div class="tabs-panel" :class="{ 'show': isActive('tab1') }" id="tab1">
        <div class="tabs-err flex" v-if="itemsTableOne.length === 0"><p>No data</p></div>
        <v-table v-else
            :items="itemsTableOne"
            :columns="columnsTable"
        />
        <v-table-mobile
            :items="itemsTableOne"
        />
      </div>
      <div class="tabs-panel" :class="{ 'show': isActive('tab2') }" id="tab2">
        <div class="tabs-err flex" v-if="itemsTableTwo.length === 0"><p>No data</p></div>
        <v-table v-else
                 :items="itemsTableTwo"
                 :columns="columnsTable"
        />
      </div>
      <div class="tabs-panel" :class="{ 'show': isActive('tab3') }" id="tab3">
        <div class="tabs-err flex" v-if="itemsTableThree.length === 0"><p>No data</p></div>
        <v-table v-else
                 :items="itemsTableThree"
                 :columns="columnsTable"
        />
      </div>
    </div>
  </div>
</template>

<script>
import VTable from "@/components/table/vTable";
import VTableMobile from "@/components/table/vTableMobile";

export default {
  name: "GeneralTable",
  components: {VTableMobile, VTable},
  props: {},
  data() {
    return {
      activeItem: 'tab1',
      itemsTableOne: [
        {
          title: 'Row Title Sample',
          name: 'Name Service',
          date: '01.05.2021',
          status: 'Complete',
          statusColor: 'circle',
          comment: 'Sample Text Comment'
        },
        {
          title: 'Row Title Sample',
          name: 'Name Service',
          date: '01.05.2021',
          status: 'Canceled',
          statusColor: 'circle-red',
          comment: 'Sample Text Comment'
        },
        {
          title: 'Row Title Sample',
          name: 'Name Service',
          date: '01.05.2021',
          status: 'Progress',
          statusColor: 'circle-blue',
          comment: 'Sample Text Comment'
        },
        {
          title: 'Row Title Sample',
          name: 'Name Service',
          date: '01.05.2021',
          status: 'Complete',
          statusColor: 'circle',
          comment: 'Sample Text Comment'
        },
      ],
      itemsTableTwo: [],
      itemsTableThree: [],
      columnsTable:['Title', 'Date', 'Status', 'Comment']
    }
  },
  methods: {
    isActive(menuItem) {
      return this.activeItem === menuItem
    },
    setActive(menuItem) {
      return this.activeItem = menuItem
    }
  }
}
</script>

<style lang="scss">
@import "@/assets/scss/main.scss";

.tabs {
  hr {
    position: relative;
    top: -2px;
    z-index: 0;
  }
  &-nav {
    position: relative;
    z-index: 2;
    overflow: auto;
    white-space: nowrap;

    &__item {
      margin-right: 30px;
      &:nth-child(3) {
        margin-right: 0;
      }
    }
    &__link {
      font-weight: 500;
      font-size: 14px;
      line-height: 16.5px;
      padding-bottom: 10px;
      &.active {
        color: $primary-color;
        border-bottom: 2px solid $primary-color;
      }

    }
  }
  &-panel {
    display: none;

    &.show {
      display: block;
    }
  }
  &-err {
    padding: 50px 0 200px 0;
    p {
      font-size: 14px;
      font-weight: 500;
      line-height: 16.4px;
      color: $form-lbl-color;
    }
  }
}
</style>
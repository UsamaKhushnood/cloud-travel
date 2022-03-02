<template>
  <v-card elevation="0">
    <v-card-text>
      <div class="d-flex align-center justify-space-between">
        <h3 class="text--primary fw-7">{{ filterTitle }}</h3>
        <v-btn
          v-if="clearable"
          color="primary"
          class="opacity-1 font-weight-bold f-12"
          plain
          small
          >clear</v-btn
        >
      </div>
    </v-card-text>
    <div class="px-4 pb-5 mr-3 position-relative">
      <div v-if="collapsable" class="collapsable">
        <div
          v-for="(option, index) in visible"
          :key="index"
          class="d-flex justify-space-between align-center filter-checks"
        >
          <v-checkbox
            :label="option.quality"
            class="mt-1"
            hide-details
          ></v-checkbox>
          <span class="count">{{ option.count }}</span>
        </div>

        <v-expand-transition>
          <div v-show="expand">
            <div
              v-for="(option, index) in sliced"
              :key="index"
              class="d-flex justify-space-between align-center filter-checks"
            >
              <v-checkbox
                :label="option.quality"
                class="mt-1"
                hide-details
              ></v-checkbox>
              <span class="count">{{ option.count }}</span>
            </div>
          </div>
        </v-expand-transition>
        <p
          class="mb-0 mt-2 primary--text f-14 fw-7 pointer"
          @click="expand = !expand"
        >
          <span v-if="!expand">Show {{ filterOptions.length - 3 }} more</span>
          <span v-else>Show less</span>
          <v-icon color="primary" :class="expand ? 'rotate-upward' : ''"
            >mdi-menu-down</v-icon
          >
        </p>
      </div>
      <div v-else>
        <div
          v-for="(option, index) in filterOptions"
          :key="index"
          class="d-flex justify-space-between align-center filter-checks"
        >
          <v-checkbox
            :label="option.quality"
            class="mt-1"
            hide-details
          ></v-checkbox>
          <span class="count">{{ option.count }}</span>
        </div>
      </div>
      <template v-if="!filterOptions">
        <div class="d-flex align-items-center justify-center">
          <h5>No Filter</h5>
        </div>
      </template>
    </div>
  </v-card>
</template>
<script>
export default {
  props: {
    filterTitle: { type: String, default: 'Filter' },
    filterOptions: {
      type: Array,
    },
    clearable: { type: [Boolean, String], default: false },
    collapsable: { type: [Boolean, String], default: false },
  },
  data() {
    return {
      expand: false,
    }
  },
  computed: {
    visible() {
      return this.filterOptions.slice(0, 3)
    },
    sliced() {
      return this.filterOptions.slice(3, this.filterOptions.length)
    },
  },
}
</script>
<style lang="scss">
.filter-checks {
  label.v-label {
    color: #000;
  }
}

.rotate-upward {
  transform: rotate(180deg);
}
</style>

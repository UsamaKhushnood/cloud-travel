<template>
  <v-card>
    <v-card-text>
      <div class="d-flex align-center justify-space-between">
        <h3 class="text--primary fw-7">Star Rating</h3>
        <v-btn
          color="primary"
          class="opacity-1 font-weight-bold f-12"
          plain
          small
          >clear</v-btn
        >
      </div>
    </v-card-text>
    <div class="px-4 pb-3 mr-3 position-relative">
      <div
        v-for="(option, index) in filterOptions"
        :key="index"
        class="d-flex justify-space-between align-center filter-checks"
      >
        <v-checkbox
          v-if="option.quality !== 0"
          :label="option.quality"
          class="mt-1"
          hide-details
        >
          <template #label>
            <v-rating
              background-color="#fff"
              color="warning"
              empty-icon="mdi-star-outline"
              full-icon="mdi-star"
              length="5"
              readonly
              size="24"
              :value="option.quality"
            ></v-rating>
          </template>
        </v-checkbox>
        <v-checkbox v-else :label="option.quality" class="mt-1" hide-details>
          <template #label>
            <label class="v-label pointer">No review</label>
          </template></v-checkbox
        >
        <span class="count">{{ option.count }}</span>
      </div>
    </div>
  </v-card>
</template>
<script>
export default {
  data() {
    return {
      filterOptions: [
        { quality: 5, count: 999 },
        { quality: 4, count: 999 },
        { quality: 3, count: 999 },
        { quality: 2, count: 999 },
        { quality: 1, count: 999 },
        { quality: 0, count: 999 },
      ],
    }
  },
}
</script>
<style lang="scss">
.filter-checks {
  label.v-label {
    color: #000;
  }
  button.v-icon.notranslate.v-icon--link.mdi.mdi-star.warning--text {
    padding: 0;
  }
}
</style>

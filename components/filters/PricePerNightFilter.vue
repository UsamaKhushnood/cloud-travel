<template>
  <v-card elevation="0">
    <v-card-text>
      <div class="d-flex align-center justify-space-between">
        <h3 class="text--primary fw-7">Price per night</h3>
        <v-btn
          color="primary"
          class="opacity-1 font-weight-bold f-12"
          plain
          small
          >clear</v-btn
        >
      </div>
    </v-card-text>
    <div class="px-4 pb-5 position-relative">
      <v-range-slider
        v-model="range"
        :max="max"
        :min="min"
        track-color="#dddddd"
        tick-size="15"
        class="range-slider"
        color="secondary"
        hide-details
      ></v-range-slider>
      <div class="d-flex align-center mt-2">
        <v-text-field
          v-model="range[0]"
          outlined
          label="SGD"
          hide-details
          solo
          dense
          class="mr-4 rangeInput"
          single-line
          type="number"
          @change="$set(range, 0, $event)"
        ></v-text-field>
        <span class="input-divider"></span>
        <v-text-field
          v-model="range[1]"
          outlined
          label="SGD"
          hide-details
          solo
          dense
          class="ml-4 rangeInput"
          type="number"
          single-line
          @change="$set(range, 1, $event)"
        ></v-text-field>
      </div>
    </div>
  </v-card>
</template>
<script>
export default {
  data() {
    return {
      min: 0,
      max: 1000,
      range: [0, 550],
    }
  },
}
</script>
<style lang="scss">
.input-divider:after {
  content: '';
  width: 16px;
  height: 1px;
  background: #757575;
  position: absolute;
  left: 50%;
  transform: translate(-50%);
}

.range-slider {
  .v-slider__track-container {
    height: 8px;
    border-radius: 5px !important;
    overflow: hidden;
  }
  .v-slider__thumb.secondary {
    width: 20px;
    height: 20px;
  }
  .v-slider__thumb.secondary:before {
    background-color: white !important;
    width: 44px;
    height: 44px;
    opacity: 1;
    transform: scale(0.3) !important;
  }
}

.rangeInput {
  .v-input__slot {
    padding-left: 45px !important;
  }
  &:before {
    content: 'SGD';
    position: absolute;
    z-index: 99;
    top: 9px;
    left: 6px;
  }
}
</style>

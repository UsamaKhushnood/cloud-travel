<template>
  <v-card>
    <v-card-text>
      <div class="d-flex align-center justify-space-between">
        <h3 class="text--primary fw-7">Hotel Name</h3>
      </div>
    </v-card-text>
    <div class="px-4 pb-3 mr-3 position-relative">
      <v-text-field
        v-model="hotelName"
        dense
        outlined
        placeholder="e.g. Hilton, Ibis ..."
        append-icon="mdi-magnify"
        hide-details
        type="search"
      ></v-text-field>
    </div>
  </v-card>
</template>
<script>
export default {
  data() {
    return {
      hotelName: null,
    }
  },
}
</script>
<style lang="scss"></style>

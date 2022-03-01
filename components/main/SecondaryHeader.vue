<template>
  <div class="secondary-header" style="margin-top: 64px">
    <v-container>
      <v-row justify="center" align="center" no-gutters>
        <v-col cols="4">
          <v-text-field
            label="Search Location"
            placeholder=""
            prepend-inner-icon="mdi-magnify"
            solo
          ></v-text-field>
        </v-col>
        <v-col cols="3" class="pl-2">
          <v-text-field label="Date Picker" solo></v-text-field
        ></v-col>
        <v-col cols="3" class="pl-2">
          <v-text-field label="Guest Dropdown" solo></v-text-field
        ></v-col>
        <v-col cols="2" class="pl-2">
          <v-btn color="secondary" block class="text-capitalize py-6 f-18" large
            >Search</v-btn
          >
        </v-col>
      </v-row></v-container
    >
  </div>
</template>
<style lang="scss">
.secondary-header {
  background-color: #002d63;
  .v-input__slot {
    margin-bottom: 0;
  }
  .v-text-field__details {
    display: none !important;
  }
}
</style>

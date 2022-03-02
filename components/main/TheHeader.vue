<template>
  <div id="the-header">
    <v-app-bar app absolute elevation="0" color="#fff">
      <v-container>
        <v-row justify="center" align="center">
          <v-col cols="3">
            <v-img
              class="mx-2"
              src="/cloudtravel-logo.png"
              max-width="225"
              contain
            ></v-img>
          </v-col>
          <v-spacer></v-spacer>
          <v-col cols="6" class="d-flex the-header-btns">
            <v-spacer></v-spacer>
            <v-menu offset-y>
              <template #activator="{ on, attrs }">
                <v-btn
                  color="dark"
                  class="font-weight-bold text-capitalize opacity-1"
                  plain
                  v-bind="attrs"
                  v-on="on"
                >
                  {{ selectedLanguage }}
                  <v-icon right dark> mdi-menu-down </v-icon>
                </v-btn>
              </template>
              <v-list class="language-menu">
                <v-list-item
                  v-for="(lang, index) in ['English', 'French', 'Chinese']"
                  :key="index"
                >
                  <v-btn
                    color="dark"
                    class="font-weight-bold text-capitalize opacity-1 listBtn"
                    plain
                    block
                    small
                    v-bind="attrs"
                    v-on="on"
                    @click="updateLang(lang)"
                  >
                    {{ lang }}
                  </v-btn>
                </v-list-item>
              </v-list>
            </v-menu>
            <v-menu offset-y>
              <template #activator="{ on, attrs }">
                <v-btn
                  color="dark"
                  class="font-weight-bold text-capitalize opacity-1"
                  plain
                  v-bind="attrs"
                  v-on="on"
                >
                  {{ selectedCurrency }}
                  <v-icon right dark> mdi-menu-down </v-icon>
                </v-btn>
              </template>
              <v-list class="currency-menu">
                <v-list-item
                  v-for="(currency, index) in ['USD', 'PKR']"
                  :key="index"
                >
                  <v-btn
                    color="dark"
                    class="font-weight-bold text-capitalize opacity-1 listBtn"
                    plain
                    block
                    small
                    v-bind="attrs"
                    v-on="on"
                    @click="updateCurrency(currency)"
                  >
                    {{ currency }}
                  </v-btn>
                </v-list-item>
              </v-list>
            </v-menu>
            <v-btn plain class="font-weight-bold text-capitalize opacity-1"
              >My Account</v-btn
            >
            <v-btn plain class="font-weight-bold text-capitalize opacity-1"
              >Login</v-btn
            >
          </v-col>
        </v-row>
      </v-container>
    </v-app-bar>
  </div>
</template>
<script>
export default {
  data() {
    return {
      selectedLanguage: 'English',
      selectedCurrency: 'USD',
      attrs: null,
      on: null,
    }
  },
  methods: {
    updateLang(lang) {
      this.selectedLanguage = lang
    },
    updateCurrency(currency) {
      this.selectedCurrency = currency
    },
  },
}
</script>
<style lang="scss">
.the-header-btns {
  span.v-btn__content {
    font-size: 16px !important;
  }
}

.language-menu,
.currency-menu {
  &.v-sheet {
    padding: 4px 0 !important;
  }
  .v-list-item {
    min-height: 30px;
    padding: 0 5px;
  }
}

button.listBtn:hover {
  background: #e2e2e29c;
}
</style>

<template>
  <v-app>
    <TheHeader />
    <SecondaryHeader />
    <v-main>
      <v-container>
        <v-row>
          <v-col cols="4" xl="2" lg="4" md="4">
            <TheSidebar />
          </v-col>
          <v-col>
            <Nuxt />
          </v-col>
        </v-row>
      </v-container>
    </v-main>
    <TheFooter />
  </v-app>
</template>

<script>
import TheHeader from '@/components/main/TheHeader.vue'
import SecondaryHeader from '@/components/main/SecondaryHeader.vue'
import TheFooter from '@/components/main/TheFooter.vue'
import TheSidebar from '@/components/main/TheSidebar'
export default {
  name: 'DefaultLayout',
  components: { TheHeader, SecondaryHeader, TheSidebar, TheFooter },
  data() {
    return {}
  },
}
</script>

<template>
  <v-app>
    <TheHeader />
    <SecondaryHeader />
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <TheFooter />
  </v-app>
</template>

<script>
import TheHeader from '@/components/main/TheHeader.vue'
import SecondaryHeader from '@/components/main/SecondaryHeader.vue'
import TheFooter from '@/components/main/TheFooter.vue'
export default {
  name: 'DefaultLayout',
  components: { TheHeader, SecondaryHeader, TheFooter },
  data() {
    return {}
  },
}
</script>

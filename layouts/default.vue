<template>
  <v-app>
    <header />
    <v-container>
      <Nuxt />
    </v-container>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
}
</script>
<style lang="scss">
header {
  height: 156px;
  background-image: url('~/assets/images/bg-header-desktop.svg');
  background-color: rgb(95, 164, 164);
}

.v-application {
  background-color: hsl(180, 52%, 96%) !important;
}
</style>

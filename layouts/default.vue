<template>
  <v-app>
    <header />
    <v-container>
      <Nuxt />
    </v-container>
    <footer>
      <div class="attribution pb-8 text-center">
        Challenge by
        <a href="https://www.frontendmentor.io?ref=challenge" target="_blank"
          >Frontend Mentor</a
        >.<br />
        Coded by <a href="#">Pham Ich Anh</a>.
      </div>
    </footer>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
};
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

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

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator';

@Component
export default class extends Vue {}
</script>
<style lang="scss">
.v-application {
  font-family: 'League Spartan', sans-serif !important;
}

header {
  background-color: rgb(95, 164, 164);
  background-repeat: no-repeat;
  background-size: 100% 100%;
}

.v-application {
  background-color: hsl(180, 52%, 96%) !important;
}

@media (min-width: 960px) {
  header {
    height: 156px;
    background-image: url('~/assets/images/bg-header-desktop.svg');
  }
}

@media (max-width: 959px) {
  header {
    height: 156px;
    background-image: url('~/assets/images/bg-header-mobile.svg');
  }
}
</style>

<template>
  <v-chip
    label
    class="pr-0 py-0 ma-2 font-weight-bold"
    color="secondary"
    text-color="primary"
  >
    <slot />
    <v-btn
      class="white--text ml-2 btn-close px-1 rounded-l-0"
      min-width="32"
      depressed
      small
      @click="$emit('delete')"
    >
      <v-icon size="18"> mdi-close-thick </v-icon>
    </v-btn>
  </v-chip>
</template>

<script>
export default {};
</script>
<style lang="scss">
.btn-close {
  height: 100% !important;
  background-color: #5fa4a4 !important;
}

.btn-close:hover {
  background-color: #2c3a3a !important;
}
</style>

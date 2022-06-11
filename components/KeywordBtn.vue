<template>
  <v-hover v-slot="{ hover }">
    <v-chip
      label
      class="ml-2 font-weight-bold"
      :color="hover ? 'primary' : 'secondary'"
      :text-color="hover ? 'white' : 'primary'"
    >
      <slot />
    </v-chip>
  </v-hover>
</template>

<script>
export default {};
</script>

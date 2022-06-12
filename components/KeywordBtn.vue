<template>
  <v-hover v-slot="{ hover }">
    <v-chip
      label
      class="font-weight-bold"
      :color="hover ? 'primary' : 'secondary'"
      :text-color="hover ? 'white' : 'primary'"
      @click="$emit('click')"
    >
      <slot />
    </v-chip>
  </v-hover>
</template>

<script>
export default {};
</script>

<template>
  <v-chip label class="font-weight-bold keyword-btn" @click="$emit('click')">
    <slot />
  </v-chip>
</template>

<script>
export default {};
</script>
<style lang="scss">
.keyword-btn {
  background-color: #eef6f6 !important;
  color: #5fa4a4 !important;
}

.keyword-btn:hover {
  background-color: #5fa4a4 !important;
  color: white !important;
}
</style>

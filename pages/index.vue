<template>
  <v-row>
    <v-col>
      <v-card v-if="filter.length > 0" class="px-9 py-5">
        <chip-btn
          v-for="item in filter"
          :key="item"
          @delete="removeItemOfFilter(item)"
        >
          {{ item }}
        </chip-btn>
      </v-card>
      <v-card></v-card>
    </v-col>
  </v-row>
</template>

<script>
import ChipBtn from '../components/ChipBtn.vue'
export default {
  name: 'IndexPage',
  components: { ChipBtn },
  data() {
    return {
      filter: ['Frontend', 'CSS', 'Javascript'],
    }
  },
  methods: {
    removeItemOfFilter(item) {
      const idx = this.filter.indexOf(item)
      this.filter.splice(idx, 1)
    },
  },
}
</script>

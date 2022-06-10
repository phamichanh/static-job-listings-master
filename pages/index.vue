<template>
  <v-row>
    <v-col>
      <v-card v-if="filter.length > 0" class="px-8 py-3">
        <div class="d-flex justify-space-between align-center">
          <div>
            <chip-btn
              v-for="item in filter"
              :key="item"
              @delete="removeItemOfFilter(item)"
            >
              {{ item }}
            </chip-btn>
          </div>
          <a class="filter__btn-clear" @click="clearFilter()"> Clear </a>
        </div>
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
    clearFilter() {
      this.filter = []
    },
  },
}
</script>
<style scoped lang="scss">
.filter__btn-clear {
  color: #7b8e8e;
  font-weight: 600;
}

.filter__btn-clear:hover {
  color: #5fa4a4;
  font-weight: 600;
  text-decoration: underline;
}
</style>

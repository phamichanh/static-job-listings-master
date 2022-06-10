<template>
  <v-row>
    <v-col>
      <v-card v-if="filter.length > 0" class="px-8 py-3 mb-10">
        <div class="d-flex justify-space-between align-center">
          <div>
            <keyword-selected-btn
              v-for="item in filter"
              :key="item"
              @delete="removeItemOfFilter(item)"
            >
              {{ item }}
            </keyword-selected-btn>
          </div>
          <a class="filter__btn-clear mr-2" @click="clearFilter()"> Clear </a>
        </div>
      </v-card>
      <job-card></job-card>
      <job-card></job-card>
      <job-card></job-card>
    </v-col>
  </v-row>
</template>

<script>
import KeywordSelectedBtn from '../components/KeywordSelectedBtn.vue'
export default {
  name: 'IndexPage',
  components: { KeywordSelectedBtn },
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

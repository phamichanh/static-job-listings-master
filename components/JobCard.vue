<template>
  <v-card class="mt-6 px-10 py-8">
    <div class="d-flex justify-space-between">
      <div class="d-flex align-center">
        <v-avatar size="90" class="mr-5">
          <v-img :src="`${job.logo}`" width="90" height="90" />
        </v-avatar>
        <v-list-item three-line class="pa-0">
          <v-list-item-content class="pa-0">
            <v-list-item-title
              class="subtitle-1 font-weight-bold primary--text"
            >
              <span class="mr-3">{{ job.company }}</span>
              <v-chip
                v-if="job.new"
                small
                color="primary"
                class="text-uppercase font-weight-bold mx-1"
              >
                New!
              </v-chip>
              <v-chip
                v-if="job.featured"
                small
                color="accent"
                class="text-uppercase font-weight-bold mx-1"
              >
                Featured
              </v-chip>
            </v-list-item-title>
            <v-hover v-slot="{ hover }">
              <h3 class="font-weight-bold">
                <a :class="`${hover ? 'primary--text' : 'accent--text'} h1`">
                  {{ job.position }}
                </a>
              </h3>
            </v-hover>
            <v-list-item-subtitle class="font-weight-medium tertiary--text">
              <span>{{ job.postedAt }}</span>
              <span class="dot-spacer mx-3"></span>
              <span>{{ job.contract }}</span>
              <span class="dot-spacer mx-3"></span>
              <span>{{ job.location }}</span>
            </v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
      </div>
      <div class="d-flex justify-end align-center">
        <keyword-btn
          v-for="word in keywords"
          :key="word"
          @click="$emit('keyword-click', word)"
        >
          {{ word }}
        </keyword-btn>
      </div>
    </div>
  </v-card>
</template>

<script lang="ts">
import { Component, Vue, Prop } from 'nuxt-property-decorator';
import { JobDto } from '../types/job';

@Component
export default class extends Vue {
  @Prop({
    type: Object,
    default: () => {
      return {};
    },
  })
  job!: JobDto;

  get keywords(): string[] {
    let keywords = [];
    keywords.push(this.job.role);
    keywords.push(this.job.level);
    keywords = keywords.concat(this.job.tools, this.job.languages);
    return keywords;
  }
}
</script>
<style lang="scss">
.dot-spacer {
  display: inline-block;
  height: 4px;
  width: 4px;
  background-color: #b7c4c4;
  border-radius: 50%;
  margin-bottom: 2px;
}
</style>

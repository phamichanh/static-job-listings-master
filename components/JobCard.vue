<template>
  <v-card
    :class="`${
      job.featured ? 'featured-active' : ''
    } featured-border mt-10 mt-md-6 pl-9 pr-10 py-md-8 pb-8 elevation-5`"
  >
    <div class="d-md-flex align-center justify-md-space-between">
      <div class="d-md-flex">
        <img
          :src="`${job.logo}`"
          alt="job-company-logo"
          class="job__company-avatar"
        />
        <v-list-item three-line class="pa-0">
          <v-list-item-content class="pa-0">
            <v-list-item-subtitle class="font-weight-bold primary--text">
              <span class="mr-2 job__company">{{ job.company }}</span>
              <v-chip
                v-if="job.new"
                small
                color="primary"
                class="text-uppercase font-weight-bold mr-1 px-2 job__tag"
              >
                New!
              </v-chip>
              <v-chip
                v-if="job.featured"
                small
                color="accent"
                class="text-uppercase font-weight-bold mr-1 px-2 job__tag"
              >
                Featured
              </v-chip>
            </v-list-item-subtitle>
            <v-list-item-title class="font-weight-bold">
              <a class="job__position">
                {{ job.position }}
              </a>
            </v-list-item-title>
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
      <v-divider class="d-block d-md-none my-4" />
      <div class="d-md-flex justify-md-end">
        <keyword-btn
          v-for="word in keywords"
          :key="word"
          class="my-1 mr-2 mr-md-0 ml-md-2"
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
    let keywords: string[] = [];
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

.featured-border {
  border-left-style: solid;
  border-left-width: 5px;
}

.featured-active {
  border-left-color: #5fa4a4 !important;
}

.job__company {
  font-size: 18px;
}

.job__tag {
  padding-top: 2px;
  font-size: 13px !important;
}

.job__position {
  color: #2c3a3a !important;
  font-size: 20px;
}

.job__position:hover {
  color: #5fa4a4 !important;
}

@media (min-width: 960px) {
  .job__company-avatar {
    height: 90px;
    width: 90px;
    margin-right: 20px;
  }
}

@media (max-width: 959px) {
  .job__company-avatar {
    height: 50px;
    width: 50px;
    margin-top: -25px;
  }
}
</style>

<template>
  <v-row>
    <v-col>
      <v-card
        :class="`${filter.length > 0 ? '' : 'd-hidden'} px-8 py-3 mb-10`"
        style="margin-top: -40px"
      >
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
      <job-card
        v-for="job in jobs"
        :key="job.id"
        :job="job"
        @keyword-click="addItemToFilter"
      />
    </v-col>
  </v-row>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator';
import KeywordSelectedBtn from '../components/KeywordSelectedBtn.vue';

@Component({
  components: {
    KeywordSelectedBtn,
  },
})
export default class extends Vue {
  filter: string[] = [];

  jobs = [
    {
      id: 1,
      company: 'Photosnap',
      logo: './images/photosnap.svg',
      new: true,
      featured: true,
      position: 'Senior Frontend Developer',
      role: 'Frontend',
      level: 'Senior',
      postedAt: '1d ago',
      contract: 'Full Time',
      location: 'USA Only',
      languages: ['HTML', 'CSS', 'JavaScript'],
      tools: [],
    },
    {
      id: 2,
      company: 'Manage',
      logo: './images/manage.svg',
      new: true,
      featured: true,
      position: 'Fullstack Developer',
      role: 'Fullstack',
      level: 'Midweight',
      postedAt: '1d ago',
      contract: 'Part Time',
      location: 'Remote',
      languages: ['Python'],
      tools: ['React'],
    },
    {
      id: 3,
      company: 'Account',
      logo: './images/account.svg',
      new: true,
      featured: false,
      position: 'Junior Frontend Developer',
      role: 'Frontend',
      level: 'Junior',
      postedAt: '2d ago',
      contract: 'Part Time',
      location: 'USA Only',
      languages: ['JavaScript'],
      tools: ['React', 'Sass'],
    },
    {
      id: 4,
      company: 'MyHome',
      logo: './images/myhome.svg',
      new: false,
      featured: false,
      position: 'Junior Frontend Developer',
      role: 'Frontend',
      level: 'Junior',
      postedAt: '5d ago',
      contract: 'Contract',
      location: 'USA Only',
      languages: ['CSS', 'JavaScript'],
      tools: [],
    },
    {
      id: 5,
      company: 'Loop Studios',
      logo: './images/loop-studios.svg',
      new: false,
      featured: false,
      position: 'Software Engineer',
      role: 'Fullstack',
      level: 'Midweight',
      postedAt: '1w ago',
      contract: 'Full Time',
      location: 'Worldwide',
      languages: ['JavaScript'],
      tools: ['Ruby', 'Sass'],
    },
    {
      id: 6,
      company: 'FaceIt',
      logo: './images/faceit.svg',
      new: false,
      featured: false,
      position: 'Junior Backend Developer',
      role: 'Backend',
      level: 'Junior',
      postedAt: '2w ago',
      contract: 'Full Time',
      location: 'UK Only',
      languages: ['Ruby'],
      tools: ['RoR'],
    },
    {
      id: 7,
      company: 'Shortly',
      logo: './images/shortly.svg',
      new: false,
      featured: false,
      position: 'Junior Developer',
      role: 'Frontend',
      level: 'Junior',
      postedAt: '2w ago',
      contract: 'Full Time',
      location: 'Worldwide',
      languages: ['HTML', 'JavaScript'],
      tools: ['Sass'],
    },
    {
      id: 8,
      company: 'Insure',
      logo: './images/insure.svg',
      new: false,
      featured: false,
      position: 'Junior Frontend Developer',
      role: 'Frontend',
      level: 'Junior',
      postedAt: '2w ago',
      contract: 'Full Time',
      location: 'USA Only',
      languages: ['JavaScript'],
      tools: ['Vue', 'Sass'],
    },
    {
      id: 9,
      company: 'Eyecam Co.',
      logo: './images/eyecam-co.svg',
      new: false,
      featured: false,
      position: 'Full Stack Engineer',
      role: 'Fullstack',
      level: 'Midweight',
      postedAt: '3w ago',
      contract: 'Full Time',
      location: 'Worldwide',
      languages: ['JavaScript', 'Python'],
      tools: ['Django'],
    },
    {
      id: 10,
      company: 'The Air Filter Company',
      logo: './images/the-air-filter-company.svg',
      new: false,
      featured: false,
      position: 'Front-end Dev',
      role: 'Frontend',
      level: 'Junior',
      postedAt: '1mo ago',
      contract: 'Part Time',
      location: 'Worldwide',
      languages: ['JavaScript'],
      tools: ['React', 'Sass'],
    },
  ];

  addItemToFilter(item: string) {
    const idx = this.filter.indexOf(item);
    if (idx >= 0) {
      return;
    }
    this.filter.push(item);
  }

  removeItemOfFilter(item: string) {
    const idx = this.filter.indexOf(item);
    if (idx >= 0) {
      this.filter.splice(idx, 1);
    }
  }

  clearFilter() {
    this.filter = [];
  }
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

.d-hidden {
  visibility: hidden !important;
}
</style>

<template>
  <v-card class="mt-6 px-10 py-8">
    <div class="d-flex align-center">
      <div class="d-flex align-center">
        <v-avatar size="90" class="mr-5">
          <img alt="Avatar" src="@/assets/images/photosnap.svg" />
        </v-avatar>
        <v-list-item three-line class="pa-0">
          <v-list-item-content class="pa-0">
            <v-list-item-title
              class="subtitle-1 font-weight-bold primary--text"
            >
              Photosnap
              <v-chip
                small
                color="primary"
                class="text-uppercase font-weight-bold mx-1"
              >
                New!
              </v-chip>
              <v-chip
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
                  Senior Frontend Developer
                </a>
              </h3>
            </v-hover>
            <v-list-item-subtitle class="font-weight-medium tertiary--text">
              <span>1d ago</span>
              <span class="dot-spacer mx-3"></span>
              <span>Full Time</span>
              <span class="dot-spacer mx-3"></span>
              <span>USA only</span>
            </v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
      </div>
      <div>
        <keyword-btn> Frontend </keyword-btn>
      </div>
    </div>
  </v-card>
</template>

<script>
export default {}
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

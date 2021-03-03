<template>
  <v-col cols="12" sm="4">
    <v-card class="pa-2" outlined tile>
      <h2>Use Vuetify Components</h2>
      <p>Vuetify provides a variety of UI components to render data.</p>
      <v-list-item-group>
        <v-chip v-for="season of data.seasons" :key="`${season}${Date.now()}`">
          {{ season }}
        </v-chip>
      </v-list-item-group>
      <p>
        To change the chips above to list items, open
        [frontend/src/components/VuetifyCard.vue] and replace the following
        code:
      </p>
      <p>[code snippet]</p>
      <p>with:</p>
      <p>[code snippet]</p>
      <p>
        Read the Vuetify docs to learn more about components:
        https://vuetifyjs.com.
      </p>
    </v-card>
  </v-col>
</template>

<script>
export default {
  name: 'VuetifyCard',
  data() {
    return {
      data: {
        seasons: ['Winter', 'Spring', 'Summer', 'Fall'],
      },
    };
  },
};
</script>

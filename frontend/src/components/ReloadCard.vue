<template>
  <v-col cols="12" sm="4">
    <v-card class="pa-2" outlined tile>
      <h2>See code changes instantly</h2>
      <p>
        When you make changes to the frontend code and save the file, the app
        will automatically reload only the module that was updated, allowing you
        to see changes instantly without having to refresh your browser.
      </p>
      <p>[Explanation]</p>
    </v-card>
  </v-col>
</template>

<script>
export default {
  name: 'ReloadCard',
};
</script>

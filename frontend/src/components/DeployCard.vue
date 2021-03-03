<template>
  <v-col cols="12" sm="4">
    <v-card class="pa-2" outlined tile>
      <h2>Deploy your app to the cloud</h2>
      <h3>Powered by [Shipyard logo]</h3>
      <p>
        Use [Shipyard] to deploy your app to the cloud, following these simple
        steps:
      </p>
      <ul>
        <li>Go to https://shipyard.build.</li>
        <li>Sign in using your GitHub credentials.</li>
        <li>
          Click Add Repository to select the repo for this starter project.
        </li>
        <li>Select the branch you'd like to deploy.</li>
        <li>Click Deploy to deploy the app!</li>
      </ul>
      <p>
        Once the app is up and running, you'll be able to see it by clicking the
        <b>View Live Environment</b> icon.
      </p>
    </v-card>
  </v-col>
</template>

<script>
export default {
  name: 'DeployCard',
};
</script>

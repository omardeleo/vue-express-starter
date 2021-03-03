<template>
  <v-col cols="12" sm="4">
    <v-card class="pa-2" outlined tile>
      <h2>Connect to a server</h2>
      <h3>Powered by [Backend logo]</h3>
      <p>
        This Vue frontend is connected to an [xxxxxx] server. Below is the
        response message we receive when we ping the server:
      </p>
      <p>[response]</p>
      <p>
        The server ping count is stored to the database. Click below to reset
        the counter:
      </p>
      <p>[reset button]</p>
      <p>
        The endpoint that resets the ping counter is located in
        [backend/src/routes/index.js]:
      </p>
      <p>[code snippet]</p>
    </v-card>
  </v-col>
</template>

<script>
export default {
  name: 'ConnectCard',
};
</script>

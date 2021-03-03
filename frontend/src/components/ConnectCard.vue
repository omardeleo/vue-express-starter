<template>
  <v-col cols="12" sm="4">
    <v-card class="pa-2" outlined tile>
      <h2>Connect to a server</h2>
      <h3>Powered by [Backend logo]</h3>
      <p>
        This Vue frontend is connected to an Express server. Below is the
        response message we receive when we ping the server:
      </p>
      <p>{{ data.response }}</p>
      <p>
        The server ping count is stored to the database. Click below to reset
        the counter:
      </p>
      <v-btn
        depressed
        elevation="2"
        color="primary"
        outlined
        @click="resetCounter"
      >
        RESET COUNTER
      </v-btn>
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
  data() {
    return {
      data: {
        response: '',
      },
    };
  },
  mounted() {
    this.fetchData();
  },
  methods: {
    async fetchData() {
      fetch('/api/v1/')
        .then((res) => res.json())
        .then(
          (result) => {
            this.data.response = result.response;
          },
          (error) => {
            console.log(error);
          }
        );
    },
    async resetCounter() {
      fetch('/api/v1/reset/')
        .then((res) => res.json())
        .then(() => this.fetchData());
    },
  },
};
</script>

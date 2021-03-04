<template>
  <v-col cols="12" sm="4">
    <v-card class="pa-2 card" outlined tile>
      <h2>Connect to a server</h2>
      <div>
        <h3>Powered by</h3>
        <img src="../assets/express.png" />
      </div>
      <p>
        This Vue frontend is connected to an Express server. Below is the
        response message we receive when we ping the server:
      </p>
      <p>{{ response }}</p>
      <p>
        The server ping count is stored to the database. Click below to
        <b>reset the counter</b>:
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
        The <b>endpoint</b> that resets the ping counter is located in
        <code>
          <a :href="url" target="_blank" rel="noopener">
            backend/src/routes/index.js</a
          ></code
        >:
      </p>
      <div class="editor-container">
        <prism-editor
          class="my-editor"
          v-model="codeSnippet1"
          :highlight="highlighter"
          :readonly="true"
        >
        </prism-editor>
      </div>
    </v-card>
  </v-col>
</template>

<script>
import { PrismEditor } from 'vue-prism-editor';
import 'vue-prism-editor/dist/prismeditor.min.css'; // import the styles somewhere

// import highlighting library (you can use any library you want just return html string)
import { highlight, languages } from 'prismjs/components/prism-core';
import 'prismjs/components/prism-clike';
import 'prismjs/components/prism-javascript';
import 'prismjs/themes/prism-tomorrow.css';

const codeSnippet1 = `101 |  router.get('/api/v1/reset', async function (req, res, next) {
102 |    const counters = await db.Counter.findAll();
103 |    const count = await resetCounter(counters[0]);
104 |    res.json({response: count})
105 |  });`;

export default {
  name: 'ConnectCard',
  components: {
    PrismEditor
  },
  data: () => ({
    response: '',
    codeSnippet1: codeSnippet1,
    url: `${process.env.VUE_APP_STARTER_REPO_URL}backend/src/routes/index.js#L101-L105`
  }),
  mounted() {
    this.fetchData();
  },
  methods: {
    async fetchData() {
      fetch('/api/v1/')
        .then(res => res.json())
        .then(
          result => {
            this.response = result.response;
          },
          error => {
            console.log(error);
          }
        );
    },
    async resetCounter() {
      fetch('/api/v1/reset/')
        .then(res => res.json())
        .then(() => this.fetchData());
    },
    highlighter(code) {
      return highlight(code, languages.js); //returns html
    }
  }
};
</script>

<template>
  <v-app>
    <v-main>
      <div
        class="d-flex flex-column flex-md-row align-sm-center mt-5 ml-5 header"
      >
        <div class="d-flex flex-column justify-center align-center mr-6">
          <img src="./assets/logo.png" width="210" />
          <p class="caption">
            Replace this with your logo:
          </p>
          <p class="caption mt-n4">
            <code>
              <a :href="logoUrl" target="_blank" rel="noopener"
                >frontend/src/assets/logo.png</a
              >
            </code>
          </p>
        </div>
        <h1 class="mt-sm-n3 mt-md-n13">
          <a :href="url1" target="_blank" rel="noopener">Vue</a>-<a
            :href="url2"
            target="_blank"
            rel="noopener"
            >Express</a
          >-<a :href="url3" target="_blank" rel="noopener">Postgres</a>-<a
            :href="url4"
            target="_blank"
            rel="noopener"
            >LocalStack</a
          >
          Starter Project
        </h1>
      </div>
      <v-container>
        <v-row>
          <ThemeCard />
          <VuetifyCard />
          <ReloadCard />
          <ConnectCard />
          <UploadCard />
          <DeployCard />
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import ThemeCard from './components/ThemeCard';
import VuetifyCard from './components/VuetifyCard';
import ReloadCard from './components/ReloadCard';
import ConnectCard from './components/ConnectCard';
import UploadCard from './components/UploadCard';
import DeployCard from './components/DeployCard';

export default {
  name: 'App',

  components: {
    ThemeCard,
    VuetifyCard,
    ReloadCard,
    ConnectCard,
    UploadCard,
    DeployCard
  },

  data: () => ({
    logoUrl: `${process.env.VUE_APP_STARTER_REPO_URL}frontend/src/assets/logo.png`,
    url1: 'https://github.com/vuejs/vue',
    url2: 'https://github.com/expressjs/express',
    url3: 'https://github.com/postgres/postgres',
    url4: 'https://github.com/localstack/localstack'
  })
};
</script>

<style lang="scss">
.my-editor {
  background: #2d2d2d;
  color: #ccc;
  width: auto;
  overflow-wrap: normal;
  font-family: Fira code, Fira Mono, Consolas, Menlo, Courier, monospace;
  font-size: 14px;
  line-height: 1.5;
  padding: 5px;
  width: 700px;
}

.editor-container {
  overflow: auto;
}

a {
  text-decoration: none;
}

.v-application code {
  background-color: transparent;
  padding: 0;
  font-size: 100%;
  font-family: source-code-pro, Menlo, Monaco, Consolas, 'Courier New',
    monospace;
  font-weight: normal;
}

p {
  font-size: 95%;
}

.card {
  height: 700px;
  padding: 10px 25px;
  overflow: auto;
}
</style>

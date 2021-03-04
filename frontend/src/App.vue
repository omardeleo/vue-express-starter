<template>
  <v-app>
    <v-main>
      <v-container>
        <v-row>
          <ThemeCard />
          <VuetifyCard />
          <ReloadCard />
        </v-row>
        <v-row>
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
    //
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
</style>

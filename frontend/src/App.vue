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
    DeployCard,
  },

  data: () => ({
    //
  }),
};
</script>

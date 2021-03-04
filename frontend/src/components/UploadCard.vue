<template>
  <v-col cols="12" sm="4">
    <v-card class="pa-2" outlined tile>
      <h2>Store files in S3, locally</h2>
      <h3>Powered by [LocalStack logo]</h3>
      <p>Click below to select and upload an image from your computer.</p>
      <p>
        The image will be <b>stored in a local S3 bucket</b>, powered by
        <b>LocalStack</b>
        - a fully functional local AWS cloud stack, and displayed below.
      </p>
      <div>
        <v-btn
          depressed
          elevation="2"
          color="primary"
          outlined
          @click="clickHandler"
        >
          UPLOAD IMAGE
        </v-btn>
        <input
          ref="uploader"
          class="d-none"
          type="file"
          accept="image/*"
          @change="submitFile"
        />
      </div>
      <v-row>
        <v-col
          v-for="filename in data.filenames"
          :key="filename"
          class="d-flex child-flex"
          cols="4"
        >
          <v-img :src="filename"></v-img>
        </v-col>
      </v-row>
    </v-card>
  </v-col>
</template>

<script>
export default {
  name: 'UploadCard',
  data() {
    return {
      data: {
        filenames: []
      }
    };
  },
  mounted() {
    this.fetchBucketFiles();
  },
  methods: {
    clickHandler() {
      this.$refs.uploader.click();
    },
    async fetchBucketFiles() {
      fetch('api/v1/files')
        .then(res => res.json())
        .then(
          result => {
            const bucket = result['Name'];
            const filenames = result['Contents']
              ? result['Contents']
                  .map(file => `${bucket}/${file['Key']}`)
                  .reverse()
              : [];
            this.data.filenames = filenames;
          },
          error => {
            console.log(error);
          }
        );
    },
    async submitFile(e) {
      e.preventDefault();
      const file = e.target.files;
      try {
        if (!file) {
          throw new Error('Please select an image');
        }
        const formData = new FormData();
        formData.append('file', file[0]);
        await fetch('/api/v1/files/upload/', {
          method: 'POST',
          body: formData
        });
        this.fetchBucketFiles();
      } catch (error) {
        alert(error);
      }
    }
  }
};
</script>

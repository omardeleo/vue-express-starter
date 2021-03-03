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
      <p>[button]</p>
      <p>[thumbnail grid]</p>
    </v-card>
  </v-col>
</template>

<script>
export default {
  name: 'UploadCard',
};
</script>

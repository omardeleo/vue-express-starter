<template>
  <v-col cols="12" sm="4">
    <v-card class="pa-2" outlined tile>
      <h2>Update Appearance</h2>
      <p>
        Modify the appearance of your app by using Vuetify's built-in themes, or
        by creating a custom theme.
      </p>
      <p>
        To switch from Dark Mode to Light Mode, open
        [frontend/src/plugins/vuetify.js] and replace the following code:
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
      <p>with:</p>
      <div class="editor-container">
        <prism-editor
          class="my-editor"
          v-model="codeSnippet2"
          :highlight="highlighter"
        >
        </prism-editor>
      </div>
      <p>[Click here] to learn more about Vuetify themes.</p>
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
import 'prismjs/themes/prism-tomorrow.css'; // import syntax highlighting styles

export default {
  name: 'ThemeCard',
  components: {
    PrismEditor
  },
  data: () => ({
    codeSnippet1: ' 7 |    theme: { dark: true }',
    codeSnippet2: ' 7 |    theme: { dark: false }'
  }),
  methods: {
    highlighter(code) {
      return highlight(code, languages.js); //returns html
    }
  }
};
</script>

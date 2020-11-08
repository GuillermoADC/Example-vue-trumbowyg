<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <trumbowyg
    v-model="form.body"
    name="body"
    :config="configs.advanced"
    placeholder="Enter your content here"
    class="form-control"
  ></trumbowyg>
</template>

<script>
import "jquery-resizable-dom/dist/jquery-resizable"; // Only required for  trumbowyg.resizimg.min.js
import Trumbowyg from "vue-trumbowyg";
import "trumbowyg/dist/ui/trumbowyg.min.css";

// Plugins are optional
import "trumbowyg/dist/plugins/colors/trumbowyg.colors.js";
import "trumbowyg/dist/plugins/colors/ui/trumbowyg.colors.min.css";
import "trumbowyg/dist/plugins/pasteembed/trumbowyg.pasteembed.js";
import "trumbowyg/dist/plugins/resizimg/trumbowyg.resizimg.min.js";

export default {
  name: "App",
  components: {
    Trumbowyg,
  },
  data() {
    return {
      form: {
        body: `<h1>Resize it</h1><h1>&nbsp; 
          <img src="https://icatcare.org/app/uploads/2018/07/Thinking-of-getting-a-cat.png" width="250" height="125"><br>
        </h1>`,
      },

      configs: {
        // http://alex-d.github.io/Trumbowyg/documentation.html#basic-options
        basic: {
          autogrow: false,
        },
        advanced: {},
        plugins: {
          resizimg: {
            minSize: 64,
            step: 16,
          },
        },
      },
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

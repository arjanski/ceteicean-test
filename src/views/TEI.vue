<template>
<div>
    <v-runtime-template :template="test"></v-runtime-template>
    <div id="tei" v-html="TEI" />
</div>
</template>

<script>
import VRuntimeTemplate from "v-runtime-template";
import CETEI from '../ceteicean/CETEI.js';
export default {
  name: 'TEITest',
  components: {
    VRuntimeTemplate
  },
  data() {
    return {
      TEI: null,
      test: `<button v-tooltip="TEI">Vue Markup & Scope Test</button>`
    }
  },
  created() {
    var CETEIcean = new CETEI()
    var self = this;
    CETEIcean.getHTML5("https://gregorovius-edition.dhi-roma.it/api/letters/G000003", function(data) {
      console.log(data.outerHTML)
      self.TEI = data.outerHTML
    })
  }
}
</script>
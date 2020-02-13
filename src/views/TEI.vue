<template>
  <div>
    TEI would go here...
    <div id="tei" v-html="teiHTML" />
  </div>
</template>

<script>
import CETEI from '../ceteicean/CETEI.js';
export default {
  name: 'TEITest',
  data() {
    return {
      teiHTML: null
    }
  },
  created() {
    var CETEIcean = new CETEI()
    CETEIcean.getHTML5("testTEI.xml", function(data) {
      console.log(data)
      // this.teiHTML = data
    })
  }
}
</script>

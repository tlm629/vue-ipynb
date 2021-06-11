<template>
  <div>
    <p>Select a .ipynb file:</p>
    <input  type="file" @change="loadfile($event.target.files)">
    <div v-html="msg"></div>
  </div>
</template>

<script>
import './prism.css'
import nb from './notebook.js'
import Prism from 'prismjs'

export default {
  name: 'VueIpynb',
  data() {
    return {
      msg: ''
    }
  },
  updated() {
    Prism.highlightAll()
  },
  methods: {
    loadfile(inputfile) {
      var ipynbHtml = this;
      var reader = new FileReader();
      reader.onload = function () {
          var ipynb = JSON.parse(this.result);
          var notebook = nb.parse(ipynb);
          var str = notebook.render();
          console.log(str);
          ipynbHtml.msg = str.innerHTML;
      };
      reader.readAsText(inputfile[0]);
    }
  }
}
</script>

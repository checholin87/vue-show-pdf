<template>
  <div id="app" class="container-fluid">
    <div class="row">
      <div class="col col-sm-8 offset-sm-2">
        <pdf
          v-for="i in document.pages"
          :src="document.src"
          :key="i"
          :page="i"
        ></pdf>
      </div>
    </div>
  </div>
</template>

<script>
import pdf from "vue-pdf";

export default {
  name: "app",
  data() {
    return {
      document: {
        src: pdf.createLoadingTask(
          "https://file-examples-com.github.io/uploads/2017/10/file-sample_150kB.pdf"
        ),
        pages: 0
      }
    };
  },
  async mounted() {
    let { numPages } = await this.document.src.promise;
    this.document.pages = numPages;
  },
  components: {
    pdf
  }
};
</script>

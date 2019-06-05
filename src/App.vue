<template>
  <div id="app" class="container-fluid">
    <div class="row">
      <div class="col col-sm-8 offset-sm-2">
        <pdf src="./pdf-sample.pdf"></pdf>
      </div>
    </div>
  </div>
</template>

<script>
import pdf from "vue-pdf";

export default {
  name: "app",
  components: {
    pdf
  }
};
</script>

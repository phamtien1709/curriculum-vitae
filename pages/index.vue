<template>
  <div>
    <client-only placeholder="Loading...">
      <pdf
        class="pdf"
        :src="require('@/static/CV_TienPN.pdf')"
        v-for="i in numPages"
        :key="i"
        :page="i"
      ></pdf>
    </client-only>
  </div>
</template>

<script>
import Card from "~/components/Card";
var vuePdf;
if (process.browser) {
  vuePdf = require('vue-pdf').default
}

export default {
  name: "HomePage",

  components: {
    Card,
    vuePdf
  },
  data() {
		return {
			src: '@/static/CV_TienPN.pdf',
			numPages: undefined,
		}
  },
  mounted() {

			this.numPages = 3;
	}
};
</script>
<style lang="css">
.pdf {
  border: 1px solid red;
  width: 100%;
  height: 100%;
}

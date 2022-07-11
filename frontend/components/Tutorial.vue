<!-- Please remove this file from your project -->
<template>
  <div class="main">
    hello world from client!

    <div class="from-server">
      {{response}}
    </div>

  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'IndexPage',
  async mounted() {
    const {data} = await axios.get('http://localhost:3001/');
    this.response = data;
  },
  data() {
    return {
      response: 'hello default'
    }
  }
}
</script>

<style lang="scss" scoped>
.main {
  color: $test-css;

  .from-server {
    color: black;
  }
}
</style>

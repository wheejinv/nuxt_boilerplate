<template>
  <Tutorial :text="text"/>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
    return {
      text: 'hello default'
    }
  },
  async mounted() {
    // 현재 클라 사이드에서 실행할 때에만 쿠키값이 셋팅됨.
    const text = await this.$axios.$get('/');
  },
  async asyncData(context) {
    const text = await context.$axios.$get('/');

    return {
      text,
    }
  }
}
</script>

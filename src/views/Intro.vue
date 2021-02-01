<!-- 组件说明 -->
<template>
   <article class="markdown-body" v-html="md"></article>
</template>

<script >
import md from "../markdown/intro.md";
export default {
  components: {},
  data() {
    return {
      md,
    };
  },
  computed: {},
  methods: {},
};
</script>

<style lang="scss" scoped>
//@import url()
</style>

<template>
  <main class="main">
    <h1 class="title">{{ title }}</h1>
    <p class="publishedAt">{{ publishedAt }}</p>
    <div class="post" v-html="body"></div>
  </main>
</template>

<script>
import axios from 'axios'

export default {
  name: 'MicrocmsNuxtJamstackBlogIndex',

  async asyncData({ params }) {
    const { data } = await axios.get(
      `https://310blog.microcms.io/api/v1/blog/${params.slug}`,
      {
        headers: { 'X-MICROCMS-API-KEY': 'f91abb870a2d48f8aa7a0e7419f36d2d9765' }
      }
    )
    return data
  }

};
</script>

<style lang="scss" scoped>

</style>
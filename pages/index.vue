<template>
  <ul>
    <li v-for="content in contents" :key="content.id">
      <nuxt-link :to="`/${content.id}`">
        {{ content.title }}
      </nuxt-link>
      
    </li>
  </ul>
</template>

<script>
import axios from 'axios'

export default {
  name: 'IndexPage',
  
  async asyncData() {
    const { data } = await axios.get(
      // your-service-id部分は自分のサービスidに置き換えてください
      'https://310blog.microcms.io/api/v1/blog',
      {
        // your-api-key部分は自分のapi-keyに置き換えてください
        headers: { 'X-MICROCMS-API-KEY': 'f91abb870a2d48f8aa7a0e7419f36d2d9765' }
      }
    )
    console.log(data);
    return data
  }
}
</script>

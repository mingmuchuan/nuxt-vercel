<template>
  <div>
    <h1>Hello world!</h1>
    <p>
      <nuxt-link to="/about">Go About</nuxt-link>
    </p>
    <ul>
      <li
        v-for="post in posts"
        :key="post.id"
      >{{ post.title }}</li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  async asyncData () {
    const { data } = await axios.get('https://jsonplaceholder.typicode.com/posts')
    return {
      posts: data
    }
  }
}
</script>

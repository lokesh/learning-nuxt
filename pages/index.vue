<template>
  <section class="container">
    <div>
      <h1>Home</h1>
      <h3>Posts</h3>
      <ul
        v-for="(post, idx) in posts"
        :key="idx"
      >
        <li>
          <nuxt-link :to="{name: 'posts-id', params: {id: post.id}}">
            {{ post.title }}
          </nuxt-link>
        </li>
      </ul>
    </div>
  </section>
</template>

<script>
export default {
  head() {
    return {
      title: 'Home page'
    }
  },
  computed: {
    posts() {
      return this.$store.state.posts.all;
    }
  }
}
</script>

<style>

</style>

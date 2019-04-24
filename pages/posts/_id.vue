<template>
  <div>
    <article>
      <h1>{{ post.title }}</h1>
      <p>Lorem ipsum</p>
    </article>

    <aside>
      <h2>Related posts</h2>
      <ul v-for="(related, idx) in relatedPosts" :key="idx">
        <li>
          <nuxt-link :to="{name: 'posts-id', params: {id: related.id }}">
            {{ related.title }}
          </nuxt-link>
          </li>
      </ul>
    </aside>

  </div>
</template>

<script>
export default {
  data() {
    return {
      id: parseInt(this.$route.params.id),
    }
  },
  head() {
    return {
      title: this.post.title
    }
  },
  computed: {
    post() {
      return this.posts.find(post => post.id === this.id)
    },
    posts() {
      return this.$store.state.posts.all
    },
    relatedPosts() {
      return this.posts.filter(post => post.id !== this.id);
    }
  }
}
</script>

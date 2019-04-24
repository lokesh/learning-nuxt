<template>
  <div>
    <h1>{{ post.title }}</h1>
    <p>Lorem ipsum</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      id: parseInt(this.$route.params.id),
      posts: [
        {
          id: 1,
          title: 'Post 1'
        },
        {
          id: 2,
          title: 'Post 2'
        },
        {
          id: 3,
          title: 'Post 3'
        }
      ]
    }
  },
  computed: {
    post() {
      return this.posts.find(post => post.id === this.id)
    }
  }
}
</script>

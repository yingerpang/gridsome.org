<template>
</template>

<script>
import PostCard from '@/components/PostCard.vue'
import Newsletter from '~/components/Newsletter'

export default {
  components: {
    PostCard,
    Newsletter
  }
}
</script>

<static-query>
query {
  posts: allBlogPost {
    edges {
      node {
        id
        title
        path
        date (format: "D. MMMM YYYY")
        timeToRead
        content
        author {
          id
          title
          path
          avatar (width: 60)
        }
        excerpt
      }
    }
  }
}
</static-query>

<template>
  <div class="phone-body">
    <div class="feed">
      <vuegram-post v-for="post in posts"
        :post="post"
        :key="posts.indexOf(post)">
      </vuegram-post>
    </div>
  </div>
</template>

<script>
import Post from './Post'

export default {
  name: 'PhoneBody',

  components: {
    'vuegram-post': Post
  },

  props: {
    posts: Array,
    filters: Array
  }
}
</script>

<style lang="scss" src="../assets/scss/phone-body.scss">
</style>

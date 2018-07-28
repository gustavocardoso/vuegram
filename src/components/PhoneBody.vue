<template>
  <div class="phone-body">
    <div class="feed" v-if="step === 1">
      <vuegram-post v-for="post in posts"
        :post="post"
        :key="posts.indexOf(post)">
      </vuegram-post>
    </div>

    <div v-if="step === 2">
      <div class="selected-image"
        :class="selectedFilter  "
        :style="{ backgroundImage: 'url(' + image + ')'}"></div>

      <div class="filter-container">
        <filter-type v-for="filter in filters"
          :filter="filter"
          :image="image"
          :key="filters.indexOf(filter)">
        </filter-type>
      </div>
    </div>
  </div>
</template>

<script>
import Post from './Post'
import FilterType from './FilterType'

export default {
  name: 'PhoneBody',

  components: {
    'filter-type': FilterType,
    'vuegram-post': Post
  },

  props: {
    filters: Array,
    image: String,
    posts: Array,
    selectedFilter: String,
    step: Number
  }
}
</script>

<style lang="scss" src="../assets/scss/phone-body.scss">
</style>

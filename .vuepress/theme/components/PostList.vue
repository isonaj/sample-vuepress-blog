<template>
	<div>  
    <h2>Posts</h2>
    <ul>
      <li v-for="(item, index) in posts">
        <a :href="item.path">{{item.title}}</a> ({{item.readingTime.text}})
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'PostList',
  computed: {
    posts() {
      return this.$site.pages.filter(item => item.frontmatter.type === 'post');
    }
  }
}
</script>

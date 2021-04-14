<template>
  <div>
    <AppNav />
    <h1>Articles</h1>
    <ul>
      <li v-for="article in articles" :key="article.slug">
        <div>
          <h2>{{ article.title }}</h2>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
import AppNav from '../../components/AppNav'

export default {
  components: {
    AppNav
  },
  async asyncData ({ $content, params }) {
    const articles = await $content('articles')
      .only(['title', 'description', 'img', 'slug', 'author'])
      .sortBy('createdAt', 'asc')
      .fetch()

    return {
      articles
    }
  }
}
</script>

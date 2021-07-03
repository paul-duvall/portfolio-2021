<template>
  <div class="articles--main-container">
    <h2>Articles</h2>
    <div class="articles--container">
      <div
        v-for="article in articles"
        :key="article.slug"
        class="article--container"
      >
        <div class="card--main">
          <div>
            <nuxtLink :to="{ name: 'blog-slug', params: { slug: article.slug } }">
              <h3>
                {{ article.title }}
              </h3>
            </nuxtLink>
            <p>
              {{ article.description }}
            </p>
            <AppButton
              button-text="Read more"
              name="blog-slug"
              :slug="article.slug"
              colour="greenColour"
              class="card--button"
            />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import AppButton from '../../components/AppButton'

export default {
  components: {
    AppButton
  },
  transition: {
    name: 'fade-in',
    mode: 'out-in'
  },
  async asyncData ({ $content, params }) {
    const articles = await $content('articles')
      .only(['title', 'description', 'img', 'slug', 'author'])
      .sortBy('createdAt', 'asc')
      .fetch()

    return {
      articles
    }
  },
  mounted () {
    this.articles.forEach((article) => {
      article.fullImageUrl = '~/assets/images/articles/' + article.img
    })
  }
}
</script>

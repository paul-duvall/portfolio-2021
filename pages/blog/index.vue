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
          <nuxtLink :to="{ name: 'blog-slug', params: { slug: article.slug } }">
            <img
              class="card--background-image"
              src="~/assets/images/articles/old-tech-smaller.jpg"
              alt="Background image"
            >
          </nuxtLink>
          <div class="card--text-area">
            <div>
              <h3>
                {{ article.title }}
              </h3>
              <p>
                {{ article.description }}
              </p>
            </div>
            <AppButton
              button-text="Read more"
              name="blog-slug"
              :slug="article.slug"
              colour="greyColour"
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
  }
}
</script>

<template>
  <div class="card--main">
    <nuxtLink :to="{ name: 'blog-slug', params: { slug: slug } }">
      <img
        class="card--background-image"
        src="~/assets/images/articles/old-tech-smaller.jpg"
        alt="Background image"
      >
    </nuxtLink>
    <div class="card--text-area">
      <h3 style="font-size: 16px;">
        {{ title }}
      </h3>
      <p style="font-size: 14px;">
        {{ description }}
      </p>
      <nuxtLink :to="{ name: 'blog-slug', params: { slug: slug } }">
        Read more
      </nuxtLink>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AppArticleCard',
  props: {
    title: {
      type: String,
      required: true
    },
    description: {
      type: String,
      required: true
    },
    slug: {
      type: String,
      required: true
    }
  }
}
</script>

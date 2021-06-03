<template>
  <div>
    <nuxt-link
      v-if="slug"
      class="button"
      :class="colour"
      :to="{ name: name, params: { slug: slug } }"
    >
      {{ buttonText }}
    </nuxt-link>
    <nuxt-link
      v-else
      class="button"
      :to="name"
    >
      {{ buttonText }}
    </nuxt-link>
  </div>
</template>

<script>
export default {
  name: 'AppButton',
  props: {
    buttonText: {
      type: String,
      required: true
    },
    colour: {
      type: String,
      required: true
    },
    name: {
      type: String,
      required: true
    },
    slug: {
      type: String,
      default: 'my-first-post',
      required: false
    }
  }
}
</script>

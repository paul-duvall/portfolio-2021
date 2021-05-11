<template>
  <a class="button" :href="route">
    {{ buttonText }}
  </a>
</template>

<script>
export default {
  name: 'AppButton',
  props: {
    buttonText: {
      type: String,
      required: true
    },
    route: {
      type: String,
      required: true
    }
  }
}
</script>

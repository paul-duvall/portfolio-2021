<template>
  <div>
    <div>Logo</div>
    <nav class="navigation">
      <ul class="navigation--list">
        <li class="navigation--list-item">
          <nuxt-link to="/">
           Home
          </nuxt-link>
        </li>
        <li>
          <nuxt-link to="/blog">
            Articles
          </nuxt-link>
        </li>
        <li><a href="#">Portfolio</a></li>
    </ul>
  </nav>
  </div>
</template>

<script>
export default {
  name: 'AppNav'
}
</script>

<style lang="scss">

</style>

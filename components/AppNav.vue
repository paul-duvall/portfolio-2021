<template>
  <div class="nav-container">
    <div class="nav-logo">
        pjd<span class="nav-logo-dot">.</span>
    </div>
    <nav class="nav-navigation--container">
      <ul class="nav-navigation--list">
        <li class="nav-navigation--list-item">
          <nuxt-link to="/" class="nav-navigation--list-link">
            Home
          </nuxt-link>
        </li>
        <li class="nav-navigation--list-item">
          <nuxt-link to="/blog" class="nav-navigation--list-link">
            Articles
          </nuxt-link>
        </li>
        <li class="nav-navigation--list-item">
          <nuxt-link to="/portfolio" class="nav-navigation--list-link">
            Portfolio
          </nuxt-link>
        </li>
      </ul>
    </nav>
  </div>
</template>

<script>

export default {
  name: 'AppNav'
}
</script>

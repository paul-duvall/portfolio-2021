<template>
  <div class="nav-container">
    <div class="nav-logo">
      pjd<span class="nav-logo-dot">.</span>
    </div>
    <nav class="nav-navigation--container">
      <button
        class="nav-navigation--burger"
        @click.prevent="toggleMenu"
      >
        x
      </button>
      <transition name="slide">
        <div
          v-if="menuIsVisible"
          class="nav-navigation--slide-menu"
        >
          <li class="nav-navigation--slide-item">
            <nuxt-link to="/" class="nav-navigation--slide-link">
              Home
            </nuxt-link>
          </li>
          <li class="nav-navigation--slide-item">
            <nuxt-link to="/blog" class="nav-navigation--slide-link">
              Articles
            </nuxt-link>
          </li>
          <li class="nav-navigation--slide-item">
            <nuxt-link to="/portfolio" class="nav-navigation--slide-link">
              Portfolio
            </nuxt-link>
          </li>
        </div>
      </transition>
      <ul
        class="nav-navigation--list"
        :class="{ 'nav-navigation--list__visible': menuIsVisible }"
      >
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
  name: 'AppNav',
  data () {
    return {
      menuIsVisible: false
    }
  },
  methods: {
    toggleMenu () {
      this.menuIsVisible = !this.menuIsVisible
    }
  }
}
</script>

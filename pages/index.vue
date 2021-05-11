<template>
  <div class="container">
    <div class="homepage--banner-content">
      <!-- left -->
      <div class="homepage--banner-content-left">
        <div class="homepage--title__primary-container">
          <h1 class="homepage--title__primary">
            Hi there.<br>
            I'm <span class="colour--accent">Paul Duvall</span>,
          </h1>
        </div>
        <div class="homepage--title__secondary-container">
          <h2 class="homepage--title__secondary">
            a junior developer<br>
            based in Norwich.
          </h2>
        </div>
      </div>
      <!-- right -->
      <div class="homepage--banner-content-right">
        <p class="colour--accent">
          I'm a self-taught developer, currently using Vue and Laravel to build applications for a small education and careers guidence organisation in Norfolk in the UK.
        </p>
        <p>I taught myself how to code whilst working as a supply teacher and have been in my first development position for around two years, working in a small team on a range of applications used by teachers and students.</p>
        <p>Since I enjoy keeping up to date with development technologies, I thought I'd build this site, mainly as a home for blog posts I write and smaller projects I'm building for fun. Stay a while and feel free to say hi!</p>
      </div>
    </div>
    <div class="homepage--button-container">
      <AppButton
        button-text="Say hello"
        route="/"
      />
      <AppButton
        button-text="I made this"
        route="/portfolio"
      />
      <AppButton
        button-text="I wrote this"
        route="/blog"
      />
    </div>
  </div>
</template>

<script>
import AppButton from '../components/AppButton'

export default {
  components: {
    AppButton
  },
  transition: {
    name: 'fade-in',
    mode: 'out-in'
  }
}
</script>

// To do!
// Navigation styling
// Button styling (component)
// Footer
// Homepage layout
// Articles - card component
// Blog layout

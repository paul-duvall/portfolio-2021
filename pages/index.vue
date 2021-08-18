// tasks
// Animations for homepage
// Something for 'say hello' - either a page or a modal
// Replace the Nuxt icon in the tab
<template>
  <div class="container">
    <!-- banner text top -->
    <div class="homepage-banner-top">
      <h1 class="homepage--title__primary">
        Hi there.<br>
        I'm <span class="colour--accent">Paul Duvall</span>,
      </h1>
    </div>
    <!-- banner text bottom -->
    <div class="homepage-banner-bottom">
      <h2 class="homepage--title__secondary">
        a junior developer<br>
        based in Norwich.
      </h2>
    </div>
    <!-- intro text -->
    <div class="homepage-intro-text">
      <p class="colour--accent">
        I'm a self-taught developer, currently using Vue and Laravel to build applications for a small education and careers guidence organisation in Norfolk in the UK.
      </p>
      <p>I taught myself how to code whilst working as a supply teacher and have been in my first development position for around two years, working in a small team on a range of applications used by teachers and students.</p>
      <p>Since I enjoy keeping up to date with development technologies, I thought I'd build this site, mainly as a home for blog posts I write and smaller projects I'm building for fun. Stay a while and feel free to say hi!</p>
    </div>
    <div class="homepage-buttons-container">
      <div>
        <AppButton
          button-text="Say hello"
          name=""
          colour="greenColour"
        />
      </div>
      <div>
        <AppButton
          button-text="I made this"
          name="portfolio"
          colour="greenColour"
        />
      </div>
      <div>
        <AppButton
          button-text="I wrote this"
          name="blog"
          colour="greenColour"
        />
      </div>
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

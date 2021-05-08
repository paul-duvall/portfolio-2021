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
        <p class="colour--accent">I'm a self-taught web sites and applications develop, currently primarily using Vue and Laravel to build applications.</p>
        <p>I'm a self-taught web sites and applications develop, currently primarily using Vue and Laravel to build applications. I'm a self-taught web sites and applications develop, currently primarily using Vue and Laravel to build applications.</p>
      </div>
    </div>
    <div>
        <button>Say hello</button>
        <button>I made this</button>
        <button>I wrote this</button>
    </div>
  </div>
</template>

<script>
export default {
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

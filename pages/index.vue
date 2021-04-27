<template>
  <div class="container">
    <div id="homepage--content">
      <!-- left -->
      <div id="homepage--content-left">
        <h1 class="title">
          Hi there.<br>
          I'm <span class="colour--accent">Paul Duvall</span>,
        </h1>
        <h2>
          a junior developer<br>
          based in Norwich.
        </h2>
        <button>Say hello</button>
        <button>I made this</button>
        <button>I wrote this</button>
      </div>
      <!-- right -->
      <div id="homepage--content-right">
        <p>I'm a self-taught web sites and applications develop, currently primarily using Vue and Laravel to build applications.</p>
        <p>I'm a self-taught web sites and applications develop, currently primarily using Vue and Laravel to build applications. I'm a self-taught web sites and applications develop, currently primarily using Vue and Laravel to build applications.</p>
      </div>
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

<style lang="scss">
  #homepage--content {
    display:flex;
    flex-direction: row;
  }

  #homepage--content-left {
    // border: 2px solid red;
  }

  #homepage--content-right {
    // border: 2px solid blue;
    flex: 1;
  }
</style>

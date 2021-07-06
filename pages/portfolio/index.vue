<template>
  <div class="projects--main-container">
    <h2>Projects</h2>
    <p class="projects--sub-title">
      A selection of my web projects, built for fun and to try out different technologies.
    </p>
    <div class="projects--cards-container">
      <div
        v-for="project in projects"
        :key="project.title"
        class="projects--card"
        :style="{ 'background-image': 'url(' + project.image + ')' }"
      >
        <div class="projects--card-content">
          <h3>{{ project.title }}</h3>
          <p>
            {{ project.info }}
          </p>
          <a :href="project.url" target="_blank">View project</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  transition: {
    name: 'fade-in',
    mode: 'out-in'
  },
  data () {
    return {
      projects: [
        {
          title: 'Lemon Tree Cafe',
          info: 'Built for a local cafe using just HTML, CSS and a little Javascript.',
          image: '/images/projects/project-lemon.jpg',
          url: 'http://lemontreecafebar.com/'
        },
        {
          title: 'Movie Quote Quiz',
          info: 'Test your knowledge of classic movie quotes! Built with jQuery.',
          image: '/images/projects/project-quote-quiz.jpg',
          url: 'https://quizzical-edison-7689de.netlify.com/'
        },
        {
          title: 'Claude\'s restaurant',
          info: 'A little bit of text about the project',
          image: '/images/projects/project-claudes.jpg',
          url: 'https://wonderful-wilson-e250a9.netlify.app'
        },
        {
          title: 'Drum Machine',
          info: 'Try out this drum machine application and lay down some sick beats! Built using React.',
          image: '/images/projects/project-drum.jpg',
          url: 'https://codepen.io/duvallpj/full/MdGBXm'
        },
        {
          title: 'Markdown Previewer',
          info: 'Preview text formatted using the markdown markup language. Built using React.',
          image: '/images/projects/project-markdown.jpg',
          url: 'https://codepen.io/duvallpj/full/zQKpBY'
        }
      ]
    }
  }
}
</script>

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
          <div class="projects--card-icons">
            <a
              class="projects--card-icon"
              :href="project.url"
              target="_blank"
              title="View project"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="24"
                height="24"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
                stroke-width="2"
                stroke-linecap="round"
                stroke-linejoin="round"
                class="feather feather-external-link"
              >
                <path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6" />
                <polyline points="15 3 21 3 21 9" />
                <line x1="10" y1="14" x2="21" y2="3" />
              </svg>
            </a>
            <a
              class="projects--card-icon"
              :href="project.gitUrl"
              target="_blank"
              title="View code"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="24"
                height="24"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
                stroke-width="2"
                stroke-linecap="round"
                stroke-linejoin="round"
                class="feather feather-code"
              >
                <polyline points="16 18 22 12 16 6" />
                <polyline points="8 6 2 12 8 18" />
              </svg>
            </a>
          </div>
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
          title: 'Boardgame Picker',
          info: 'Uses an API from the website Boardgamegeek. Built using Vue and Bootstrap-Vue.',
          image: '/images/projects/project-boardgame.jpg',
          url: 'https://lucid-hawking-33f455.netlify.app',
          gitUrl: 'https://github.com/paul-duvall/boardgame-picker'
        },
        {
          title: 'Lemon Tree Cafe',
          info: 'Built for a local cafe using just HTML, CSS and a little Javascript.',
          image: '/images/projects/project-lemon.jpg',
          url: 'http://lemontreecafebar.com/',
          gitUrl: 'https://github.com/paul-duvall/lemon-tree'
        },
        {
          title: 'Movie Quote Quiz',
          info: 'Test your knowledge of classic movie quotes! Built with jQuery.',
          image: '/images/projects/project-quote-quiz.jpg',
          url: 'https://quizzical-edison-7689de.netlify.com/',
          gitUrl: 'https://github.com/paul-duvall/movie-quote-quiz'
        },
        {
          title: 'Claude\'s restaurant',
          info: 'Keeping it simple on this one, built with HTML and CSS, with only the smallest amount of Javascript',
          image: '/images/projects/project-claudes.jpg',
          url: 'https://wonderful-wilson-e250a9.netlify.app',
          gitUrl: 'https://github.com/paul-duvall/Claudes-restaurant'
        },
        {
          title: 'Drum Machine',
          info: 'Try out this drum machine application and lay down some sick beats! Built using React.',
          image: '/images/projects/project-drum.jpg',
          url: 'https://codepen.io/duvallpj/full/MdGBXm',
          gitUrl: 'https://codepen.io/duvallpj/pen/MdGBXm'
        },
        {
          title: 'Markdown Previewer',
          info: 'Preview text formatted using the markdown markup language. Built using React.',
          image: '/images/projects/project-markdown.jpg',
          url: 'https://codepen.io/duvallpj/full/zQKpBY',
          gitUrl: 'https://codepen.io/duvallpj/pen/zQKpBY'
        }
      ]
    }
  }
}
</script>

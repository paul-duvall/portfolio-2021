---
title: Setting up Tailwind in your Vue project 
description: Tailwind CSS is increasingly popular and, since I had only used Bootstrap-Vue in my work, I thought it time to try something different. If you want to try it too and want to set up a Vue project to get started in...
img: tailwind-vue-setup.jpg
alt: Setting up Tailwind in your Vue project 
---

<sub><sup>Photo by <a href="https://unsplash.com/@lgtts?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Ilse Orsel</a> on <a href="https://unsplash.com/s/photos/street-art?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a></sup></sub>
  
# Setting up Tailwind in your Vue Project

**I suspect that Tailwind CSS needs no introduction. This 'utility-first, fully responsive CSS framework' is increasingly popular (the State of CSS survey suggests it experienced the greatest degree of growth of any CSS framework in 2020) and, since I had only used Bootstrap-Vue in my work, I thought it time to try something different. If you want to try it too and want to set up a Vue project to get started in, follow these instructions.**

Instructions for setting Tailwind up in a project can be found in the [Tailwind docs](https://tailwindcss.com/docs/installation).

If you already have a Vue project set up and ready to use Tailwind, you can skip steps 1-2!

## 1. Vue CLI 

In order to easily set Vue projects up from the command line, you'll need the [Vue-cli](https://cli.vuejs.org/) (command line interface) tool installed on your computer. You can do this from the command line:

```
npm install -g @vue/cli
```

(Note that the -g adds the package globally so it can be used in all project on your computer.)

## 2. Create a Vue project

With the Vue CLI installed, you are now able to create Vue projects from the command line. Navigate to the folder on your computer where you wish to create your project and enter the follow:

```
vue create tailwind-project
```

I've chosen to call my project 'tailwind-project' but of course you can call yours whatever you wish. You'll need to select whether you want your project to use Vue 2 or 3. Once your project has been created, your command line will prompt you to type the following two commands:

```
cd tailwind-project
npm run serve
```

The first command will move you into the project folder (if you have named your project differently, you will need to replace 'tailwind-project' with the name of your project). The second command will start a development server, enabling you to view the newly-created project.

Once you have run this second command, you'll be given a localhost url, which you can copy to your browser and will show you the Vue project template:

![alt text](/images/articles/tailwind-vue-setup-vue-project-template.jpg)

## 3. Setting up Tailwind 

Back on the command line, making sure you are now in your project folder, run the following command:

```
npm install tailwindcss
```
With Tailwind installed, open your code editor of choice. You will need to create a file in the root directory of your new project called postcss.config.js and add the following to this file:

```javascript
module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  },
}
```
PostCSS is a tool that Tailwind requires in order to work ([click here](https://postcss.org/) if you want to find out more). 

You'll also need to create a file called tailwind.css in the src/assets folder in your project. Add the following to this file:

```javascript
@tailwind base;
@tailwind components;
@tailwind utilities;
```
Essentially this is your css file and these directives allow you access to all of the css classes that come with Tailwind.

Finally, in your main.js file, you'll need to import your new tailwind.css file (on a line after the import statements for Vue and App):

```javascript
import Vue from 'vue';
import App from './App.vue';
import '@/assets/css/tailwind.css';
```
## 4. PostCSS gotcha

Whilst completing this process, I hit the following error:

```
Syntax Error: Error: PostCSS plugin tailwindcss requires 
PostCSS 8.
```
You can skip this step if you don't hit this error, but if you do, follow the instructions on [this page](https://tailwindcss.com/docs/installation#post-css-7-compatibility-build).

## 5. Test it out!

All being well, you should now be able to apply a Tailwind class to you application and see the styling adjust accordingly. In the app.vue file, remove all the standard styling that is automatically included with the Vue standard template.

That done, if you view your site in the browser, you should notice that the layout and styling changes. Back in your code editor, navigate to HelloWorld.vue, the component that is automatically included. This contains the majority of the template content. You should be able to find an `<h1>` tag that renders a prop passed from the App.vue (it's the main heading that reads 'Welcome to your Vue.js app').

Add the class 'text-red-500', so the line should now read:

```html
<h1 class="text-red-500">{{ msg }}</h1>
```

If all is working, your text should now be red. Congratulations, you have successfully set up a Vue project with Tailwind!
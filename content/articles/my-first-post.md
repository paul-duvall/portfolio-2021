---
title: Setting up Tailwind in your Vue project 
description: Tailwind CSS is increasingly popular and, since I had only used Bootstrap-Vue in my work, I thought it time to try something different. If you want to try it too and want to set up a Vue project to get started in...
img: first-blog-post.jpg
alt: Setting up Tailwind in your Vue project 
---

I suspect that Tailwind CSS needs no introduction. This 'utility-first, fully responsive CSS framework' is increasingly popular (the State of CSS survey suggests it experienced the greatest degree of growth of any CSS framework in 2020) and, since I had only used Bootstrap-Vue in my work, I thought it time to try something different. If you want to try it too and want to set up a Vue project to get started in, follow these instructions.

Instructions for setting Tailwind up in a project can be found in the Tailwind docs.

If you already have a Vue project set up and ready to use Tailwind, you can skip steps 1-2!

## 1. Vue CLI 

In order to easily set Vue projects up from the command line, you'll need the Vue-cli (command line interface) tool installed on your computer. You can do this from the command line:

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
---
title: How to set up Media Queries in Sass
description: A breakdown of how the use of various features of Sass, such as mixins, can be used to make media queries more user-friendly...
img: sass-and-media-queries.jpg
alt: Well-organised stationery
---

<sub><sup>Photo by <a href="https://unsplash.com/@punttim?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Tim Gouw</a> on <a href="https://unsplash.com/s/photos/organise?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a></sup></sub>

## Sass and Media Queries

**Ensuring websites and applications are responsive so that they are usable and visually appealing across all devices is one of the cornerstones of modern web development. Writing media queries in CSS is the most commonly used technique for ensuring our products are responsive and using media queries in conjunction with Sass makes them all the easier to work with.**

In this article, I will give a brief overview of how media queries are used to ensure sites and applications are responsive and then how they can be used with the Sass preprocessing language.

An example of these ideas in practice can be found [here](https://codepen.io/duvallpj/pen/xoqLBr).

## Media Queries

A media queries can be applied in CSS to enable different values to be given to properties of selectors based upon the width of the viewport.

```css
h1 {
  font-size: 26px;
}

@media only screen and (max-width: 900px) {
  h1 {
    font-size: 24px;
  }
}
```

The above example contains a CSS rule that sets a value of 26px for the `<h1>` selector. This dictates the size of the font until the screen width drops below a breakpoint of 900px, at which point the media queries kicks in and adjusts the font size to 24px.

One media query tends to be set for each breakpoint and that one query contains all the CSS rules that need to be adjusted.

This is all well and good and media queries established in this way have served me well. However, my media queries are often located quite a long way from the CSS rules they are adapting. Imagine that the h1 rule above is located near the top of the CSS document, say around line 15. If the document were several hundred lines long and the media query located at the bottom, perhaps around line 250, it would be tricky to navigate quickly between the two.

I often find myself scrolling up and down, having looked at a rule in the media query, trying to find the original code further up the document.

## Sass and media queries

With Sass, it is possible to nest a media query directly within the CSS rule:
 
```css
h1 {
  font-size: 26px;

  @media (max-width: 900px) {
    font-size: 24px;
  }
}
```

This removes the need the name the CSS rule twice, making the code more succinct. It also ensures that all the code related to this particular rule is located in the same place.

No more scrolling up and down, hunting for two (or three or four – if multiple media queries affect the h1 rule) associated blocks of code.

## An issue

Writing media queries in this way presents a new problem – instead of having a media query defined in one place, there might be as many smaller media queries as there are rules within the CSS document.

This would be a problem if in the future you needed to adjust the breakpoint value from, say, 900px to 950px. It would be necessary to scroll through the entire codebase, hunting down dozens of media queries.

## Mixins to the rescue!

Luckily, mixins can solve this issue by allowing us to define the media query in one location and to then apply it around the codebase wherever it is needed.

```css
  @mixin respond-medium {
    @media (max-width: 900px) { @content }
  }
```

The content directive – `@content` – allows us to pass a block of code into the mixin. Once the mixin is set up, we can apply it:

```css
h1 {
  font-size: 26px;

  @include respond-medium {
    font-size: 24px;
  }
}
```

## Multiple media queries

We can go one step further to establish one mixin that handles multiple media queries, allowing us to set different breakpoints easily.

```css
  @mixin respond($breakpoint) {
    @if($breakpoint == medium)  {
      @media (max-width: 900px) { @content }
    }
    @if($breakpoint == small)  {
      @media (max-width: 600px) { @content }
    }
  }
```

Here we have established a variable called `$breakpoint`. Depending upon what is passed in for this variable (medium or small), the correct media query is set. 

With this done, we can easily apply multiple media queries:

```css
h1 {
  font-size: 26px;
  @include respond(medium) {
     font-size: 24px;
   }
  @include respond(small) {
     font-size: 20px;
   }
}
```

This example would ensure that the h1 font-size, normally 26px, would be 24px in viewports less than 900px wide and 20px in viewports less than 600px wide.

## Summary

Take a look at [this example](https://codepen.io/duvallpj/pen/xoqLBr) of media queries in Sass implemented in a real-world example. Thanks to Sass’s ability to nest items within a CSS rule, media queries can be more closely linked to the CSS rule, resulting in a codebase that is more user-friendly and understandable. This, coupled with the use of mixins (using `@content` and `@if` directives) has completely changed how I will be using media queries in the future.
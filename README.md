# Frontend Mentor - Results summary component solution

This is a solution to the [Results summary component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/results-summary-component-CE_K6s0maV). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the interface depending on their device's screen size
- See hover and focus states for all interactive elements on the page
- **Bonus**: Use the local JSON data to dynamically populate the content

### Screenshot

![](./![alt text](image.png))

### Links

- Solution URL: (https://github.com/korcakSEA/results-summary-component-main.git)
- Live Site URL: (https://korcaksea.github.io/results-summary-component-main/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- Mobile-first workflow

### What I learned

For me there are two main things to learn:
- Thought process
- Usage of variables

You can see my notes and code snippets below:


```css
  /***** plain hsl values defines in the root *****/
:root{
    --clr-accent-1: 0, 100%, 67%;
    --clr-accent-2: 39, 100%, 56%;
    --clr-accent-3: 166, 100%, 37%;
    --clr-accent-4: 234, 85%, 45%;
}
/* usage of plain hsl values */
.summary-item{
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem;
    border-radius:.5rem ;
    background-color: hsl(var(--item-color), .1);
}

/* All removed stroke values will be re-defined below*/
.summary-item svg{
    stroke: hsl(var(--item-color));
}

.summary-item__title {
  color: hsl(var(--item-color));
  font-weight: var(--fw-bold);
} 

.summary-item[data-item-type="accent-1"] {
  --item-color: var(--clr-accent-1);/*all accent values defined as plain values, without hsl brackets (). 
  So the values can be used in every variable defined.Kinde of globally defined. 
  --clr-accent-1: 0, 100%, 67%; Now --item-color: 0, 100%, 67%. 
  So in .summary-item__title class it becomes title and here .summary-item svg, it becomes svg color. 
  Here it comes the advantage of using attribute selector.
  So by changing any value here: --clr-accent-1: 0, 100%, 67%, all background,
  title and svg color will be changed for specific summary item*/
}
.summary-item[data-item-type="accent-2"] {
  --item-color: var(--clr-accent-2);
}
.summary-item[data-item-type="accent-3"] {
  --item-color: var(--clr-accent-3);
}
.summary-item[data-item-type="accent-4"] {
  --item-color: var(--clr-accent-4);
}

/***** DEfined variables in parent *****/
.result-summary{
    --border-radius:2rem;/* we will define it here but use it in media qurey*/
    --padding:2.5rem; /*Children (result and summary) inherit*/
    max-width: 46rem;
    display: grid;
}

.section-title{
    font-weight: var(--fw-bold);
    font-size: var(--font-md);
}

.result{
    text-align: center;
    background: linear-gradient(var(--gradientBg-slate-blue), var(--gradientBg-royal-blue));
    color:hsla(0, 0%, 100%, 0.6) ;
    border-radius: 0 0 var(--border-radius) var(--border-radius);/* definition for each corner*/
}

.result,
.summary{
    padding:var(--padding)
} 

/***** Grid flow: centering and aligning items *****/
.grid-flow{
    display: grid;
    align-content: start; /* if not used, grid will strech out. 
    with the help of align-content layout is very nicely organized*/
    gap: 1rem;
}

.grid-flow[data-spacing="large"]{
    gap: 2rem; /* by selecting attribute can choose specific 
    element to prevent inheriting from parent*/
    /* That`s really nice! we still use gap property but elements 
    that has this attribute have gap with 2 rem,
    instead of defining any margin-buttom */
}

.result-score{
    display: grid;
    place-content: center;
    /* Above is another technique to center */
    width: 12rem;
    aspect-ratio: 1/1;/* to have a perfect circle*/
    margin-inline: auto;
    background:linear-gradient(hsla(256, 72%, 46%, 1),hsla(241, 72%, 46%, 0));
    border-radius: 50%;
}

```


### Useful resources

- [Example resource 1](https://www.youtube.com/watch?v=KqFAs5d3Yl8&t=1126s) - I took the provided link as reference due to understanding thought process from design to code. Thanks to Kevin Powel for the video.



## Author

- Frontend Mentor - [@korcakSEA](https://www.frontendmentor.io/profile/korcakSEA)


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
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the interface depending on their device's screen size
- See hover and focus states for all interactive elements on the page
- **Bonus**: Use the local JSON data to dynamically populate the content

### Screenshot

![](./screenshots/screenshot-1.jpg)
![](./screenshots/screenshot-2.jpg)

### Links

- Solution URL: [Add solution URL here](https://your-solution-url.com)
- Live Site URL: [Add live site URL here](https://your-live-site-url.com)

## My process

### Built with

- CSS custom properties
- Flexbox
- CSS Grid
- Mobile-first workflow
- JavaScript 

### What I learned

- how to fetch JSON file using JS and display data on the webpage

```js
fetch('./data.json')
      .then(res => res.json())
      .then(data => {
        data.forEach(skill => {
          document.querySelector('.js-skills-grid').insertAdjacentHTML('beforeend', `<div class="${skill.category.toLowerCase()} skill">
              <span class="skill-label"><img src=${skill.icon} class="js-icon"> ${skill.category}</span>
              <p class="skill-score"><span>${skill.score}</span> / 100</p>
              </div>
            </div>`)
        })
      });
```

- how to make a smooth transition on an element with gradient 

```css
.summary > button {
	position: relative;
	width: 100%;
	height: 55px;
	margin-top: 20px;
	border: none;
	border-radius: 30px;
	font-size: 1.8rem;
	font-weight: 600;
	color: hsl(221, 100%, 96%);
	background-color: hsl(224, 30%, 27%);
	transition: background-color 0.3s ease;
	cursor: pointer;
	z-index: 1;
}
.summary > button::before {
	position: absolute;
	content: '';
	top: 0;
	right: 0;
	bottom: 0;
	left: 0;
	border-radius: 30px;
	background-image: linear-gradient(hsl(252, 100%, 67%), hsl(241, 81%, 54%));
	z-index: -1;
	transition: opacity 0.3s ease-in-out;
	opacity: 0;
}

.summary > button:hover::before {
	opacity: 1;
}
```

## Author

- Frontend Mentor - [@em-ewaa](https://www.frontendmentor.io/profile/em-ewaa)

# Marlow Clay

A responsive homepage for **Marlow Clay**, an imagined small-batch ceramics studio. Built with HTML and CSS, using flexbox for the entire layout.

This is my solution to the Codecademy challenge project **Company Home Page with Flexbox**.

<!-- Add a screenshot of the finished page here, e.g. ![Marlow Clay homepage](screenshot.png) -->

**Live site:**https://jobrophoto.github.io/marlow-clay/

## Features

- Sticky-free, wrapping navbar with an emoji logo and hover transitions on the links
- Hero section with a headline, short intro, and splash image
- About section with the photo on the opposite side from the hero
- A product collection of four cards, each showing an image, title, color, dimensions, and price
- A team section with an avatar, name, and role for each person
- A footer with the studio hours
- Responsive layout that reflows from desktop to phone without needing many media queries

## How flexbox is used

| Section        | What it does                                                                                                                                                                                                                                                |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Navbar         | `justify-content: space-between` puts the logo and links on opposite ends, `align-items: center` lines them up, and `flex-wrap` stops them colliding on small screens.                                                                                      |
| Hero and About | Each section is a wrapping flex row. The text and image both use `flex: 1 1 300px`, so they share the row on wide screens and stack on narrow ones. The About section uses `flex-direction: row-reverse` to flip the order without changing the HTML.       |
| Product list   | A wrapping flex row where each card has a `flex-basis` of 400px, so the cards form a 2x2 grid and collapse to a single column as the page shrinks. Each card is also a flex container with `flex-direction: column` to stack its image, title, and details. |
| Team           | A wrapping, centered flex row. Each member is a column flex container that centers the avatar, name, and role.                                                                                                                                              |
| Footer         | Centers its content with `justify-content: center`.                                                                                                                                                                                                         |

The `flex` shorthand (`flex-grow`, `flex-shrink`, `flex-basis`) is used throughout, and `min-width: 0` on the images stops them from forcing their flex rows to wrap early.

## Design choices

**Colors**, pulled from the product photos:

| Name     | Hex       | Used for          |
| -------- | --------- | ----------------- |
| Oat      | `#f4f1ec` | Page background   |
| Charcoal | `#2b2b2a` | Text and borders  |
| Sand     | `#e4ddd2` | Navbar and footer |
| Sage     | `#9db08f` | Team section      |
| Clay     | `#b5532b` | Hover accent      |

**Fonts** (from Google Fonts):

- [Fraunces](https://fonts.google.com/specimen/Fraunces) for headings
- [DM Sans](https://fonts.google.com/specimen/DM+Sans) for body text

All colors and fonts are defined as CSS custom properties at the top of the stylesheet, so they can be changed in one place.

## Project structure

```
marlow-clay/
├── index.html
├── css/
│   └── stylesheet.css
├── image/
│   ├── hero-img.jpg
│   ├── about-us-img.jpg
│   ├── night-mug.jpg
│   ├── harbor-bowl.jpg
│   ├── cabbage-vase.jpg
│   └── dune-plate.jpg
└── README.md
```

## Running it locally

No build step or dependencies are needed.

1. Clone or download this repository.
2. Open `index.html` in your browser.

An internet connection is needed to load the Google Fonts.

## Accessibility notes

- Semantic elements (`header`, `nav`, `main`, `section`, `article`, `footer`) and a single `h1`
- Descriptive alt text on every content image
- Decorative emoji are hidden from screen readers with `aria-hidden="true"`
- Visible hover states on links

## What I practiced

- Choosing between flex container and flex item properties, and using both on the same element
- Building a layout that adapts through `flex-wrap` and `flex-basis` rather than relying on lots of breakpoints
- Cropping images consistently with `aspect-ratio` and `object-fit: cover`
- Organizing CSS with variables and grouped selectors

## Credits

- Photos: [Unsplash photo](https://unsplash.com/)
- Fonts: Google Fonts
- Project prompt: [Codecademy](https://www.codecademy.com)

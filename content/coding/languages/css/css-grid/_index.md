---
title: "CSS Grid"
date: 2021-05-18T15:55:39+02:00
draft: false
---

[SOURCE](https://grafikart.fr/tutoriels/grid-css-1002)  

### General

```html
<div class="grid">
    <div class="element a grid-item">Element 1</div>
    <div class="element b">Element 2</div>
    <div class="element c">Element 3</div>
    <div class="element d">Element 4</div>
</div>
```

```css
/* Grid setup */

.grid {
    display: grid;
    grid-template-rows: 2fr 6r 2fr;
    grid-template-columns: 1fr 2fr;

    /* shortcut */
    /* grid-template: 2fr 6r 2fr / 1fr 2fr; */

    /* Space between rows */
	grid-row-gap: 20px;
	grid-column-gap: 10px;
    /* shortcut */
	/* grid-gap: 20px 10px; */
}

/* Items positions */

.grid-item {
    grid-column-start: 1;
    grid-column-end: 3;
    grid-row-start: 2;
    grid-row-end: span 3;
    /* 3 line sized */
}
```

![css_grid.PNG](/coding/languages/css/css-grid/css_grid.PNG)

### Item position by name

```css
.grid {
	display: grid;
    grid-template-rows: auto;
    grid-template-columns: repeat(4, 50px);
	grid-template-areas: 
    "a a a a"
    "b b . c"
    "d d d d";
}

.element.a {
    grid-area: a;
}

.element.b {
    grid-area: b;
}

.element.c {
    grid-area: c;
}

.element.d {
    grid-area: d;
}
```
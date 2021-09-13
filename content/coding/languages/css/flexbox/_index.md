---
title: "Flexbox"
date: 2021-05-18T15:55:39+02:00
draft: false
---

[SOURCE](https://openclassrooms.com/fr/courses/1603881-apprenez-a-creer-votre-site-web-avec-html5-et-css3/3298561-faites-votre-mise-en-page-avec-flexbox)  

#### General :

```
-Flex container (wrapper)
    -Flex items (element inside wrapper)
```

**2 axis** :  
-main axis (set by **flex-direction**)  
-cross axis

-alignement main axis = justify-content  
-alignement cross axis = align-items

**flex-direction** : 
- row
- column
- row-reverse
- column-reverse

```html  
<div class="wrapper">
    <div class="element">Element 1</div>
    <div class="element">Element 2</div>
    <div class="element">Element 3</div>
    <div class="element">Element 4</div>
</div>
```

```css
.wrapper
{
  display:flex;
  flex-direction: row;
  flex-wrap: wrap; /* Line break */
}
```
![flexbox-basic.png](/coding/languages/css/flexbox/flexbox-basic.png)


**Order elements -> order** : 
```css
.element.a
{
    order: 1;
}
```

**Resize -> flex** :
```css
.element.a
{
    flex: 2;
}
.element.b
{
    flex: 1;
}
```
---
title: "Demo"
date: 2021-05-18T15:55:39+02:00
draft: false
---

### HTML :
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Demo</title>
  </head>
  
  <body>
    
    <div class="wrapper basic">
      <div class="element a">Element 1</div>
      <div class="element b">Element 2</div>
      <div class="element c">Element 3</div>
      <div class="element d">Element 4</div>
    </div>
    
    <br>
    
    <div class="wrapper justify-content">
      <div class="element a">Element 1</div>
      <div class="element b">Element 2</div>
      <div class="element c">Element 3</div>
      <div class="element d">Element 4</div>
    </div>
  
    <br>
    
    <div class="wrapper full-centered">
      <div class="element a">Element 1</div>
      <div class="element b">Element 2</div>
      <div class="element c">Element 3</div>
      <div class="element d">Element 4</div>
    </div>
    
    <br>
    
    <div class="wrapper align-lines">
      <div class="element a">Element 1</div>
      <div class="element b">Element 2</div>
      <div class="element c">Element 3</div>
      <div class="element d">Element 4</div>
    </div>
      
  </body>
  
</html>
```

### CSS :
```css
.wrapper {
  display:flex;
}

.basic {
  flex-direction: row;
  flex-wrap: wrap; /* Line break */
}

.justify-content {
  flex-direction: row;
  justify-content: space-around;
}

.full-centered {
  height: 100px;
  background-color: grey;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}

.wrapper.align-lines {
  height: 75px;
  flex-wrap: wrap;
  background-color: grey;
  flex-direction: column;
  align-content: flex-end;
}

.wrapper.align-lines .element {
  width: 500px;  
}

.wrapper.full-centered .element {
  margin:auto;
}

.wrapper.basic .element {
  width: 500px;
}

.element.a {
 background-color: yellow;
}

.element.b {
 background-color: blue;
}

.element.c {
 background-color: green;
}

.element.d {
 background-color: red;
}
```
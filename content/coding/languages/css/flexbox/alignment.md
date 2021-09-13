---
title: "Alignment"
date: 2021-05-18T15:55:39+02:00
draft: false
---

#### Alignment :

**Align main axis -> justify-content :**
- flex-start (align with beginning)
- flex-end
- center
- space-between (elements are stretch on axis)
- space-around (same that space-between but with space on edges)
- stretch  (by default)

![flexbox-justify_content.png](/coding/languages/css/flexbox/flexbox-justify_content.png)

**Align horizontally & vertically :**
```css
.wrapper
{
    display: flex;
}

.element
{
    margin: auto;
}
```

**Align cross axis -> align-items** : 
- stretch
- flex-start
- flex-end
- center
- baseline

**Align lines -> align-content**

- flex-start 
- flex-end
- center
- space-between 
- space-around 
- stretch  (by default)

![flexbox-align_content.png](/coding/languages/css/flexbox/flexbox-align_content.png)
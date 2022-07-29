

The most common use of the [[HTML Picture Tag|⟨picture⟩]] element will be for art direction in responsive designs. Instead of having one image that is scaled up or down based on the viewport width, multiple images can be designed to more nicely fill the browser viewport.

The [[HTML Picture Tag|⟨picture⟩]] element contains two tags: one or more [[HTML Source Tag|⟨source⟩]] tags and one [[HTML Img Tag|⟨img⟩]] tag.

The browser will look for the first [[HTML Source Tag|⟨source⟩]] element where the media query matches the current viewport width, and then it will display the proper image (specified in the `srcset` attribute). The [[HTML Img Tag|⟨img⟩]] element is required as the last child of the [[HTML Picture Tag|⟨picture⟩]] element, as a fallback option if none of the source tags matches.

Tip: The [[HTML Picture Tag|⟨picture⟩]] element works "similar" to [[HTML Video Tag|⟨video⟩]] and [[HTML Audio Tag|⟨audio⟩]]. You set up different sources, and the first source that fits the preferences is the one being used.

```html
<picture>
  <source media="(min-width:650px)" srcset="img_pink_flowers.jpg">
  <source media="(min-width:465px)" srcset="img_white_flower.jpg">
  <img src="img_orange_flowers.jpg" alt="Flowers" style="width:auto;">
</picture>
```

<picture>
  <source media="(min-width:650px)" srcset="img_pink_flowers.jpg">
  <source media="(min-width:465px)" srcset="img_white_flower.jpg">
  <img src="img_orange_flowers.jpg" alt="Flowers" style="width:auto;">
</picture>

- Reference:
  - <https://www.w3schools.com/TAGS/tag_picture.asp>
  

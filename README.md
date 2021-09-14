# Responsive Site Template

This is a quick guide to the more complicated visual components that aren't just `<p>` tags.

## Hero Image

The hero image section, if applicable, should be placed immediately after the closing of the <header> tag. The hero section markup should follow this format:

```
<section class="hero">
    <picture>
        <!--
             hero-smallest.png is 800px wide, and the smallest size we want to render,
             so we render only when the viewport is less than 800px (media query attr)
        -->
        <source srcset="./images/hero-smallest.png"
                media="(max-width: 799px)">
        <!--
            hero-small.png is 1200px wide, so we render only when viewport
            is between 800px and 1200px (or 1px short, personal call)
        -->
        <source srcset="./images/hero-small.png"
                media="(min-width: 800px) and (max-width: 1199px)">
        <!--
            hero-default.png is 1800px wide, our largest image, so we render
            when the viewport is wider than the last step, 1200px in this case
        -->
        <source srcset="./images/hero-default.png"
                media="(min-width: 1200px)">

        <!-- fallback for unsupported browsers -->
        <img src="./images/hero-default.png" alt="Hero Image">
    </picture>
</section>
```

The <source> tags can be as many or as few as needed based on available image size variations for the hero image. Just ensure the media queries set don't overlap, that way there is high confidence as to when a specific image will load based on viewport width.
  
## Text Over Image
  
This applies to all images within the main content regardless if there's going to be text rendered over it or not. The default style here applies to images that have a landscape aspect ratio.
  
If the image is going to have a portrait aspect ratio, please add a class of `tall-image` to the opening section tag like so: `<section class="text-over-image tall-image">`
  
```
<section class="text-over-image">
    <div class="text-block">
        <!--
            if you only want the image, keep an empty
            <div class="text-block"></div> as this is
            required for proper image rendering
        -->
        <p>Lorem ipsum dolor sit amet, consectetur elit.</p>
        <p>Dolor sit amet consectetur adipiscing elit duis.</p>
        <p>Porttitor eget dolor morbi varius sit amet.</p>
    </div>
    <picture>
        <!-- Same concept about <source> tags apply here -->
        <source srcset="./images/wide-smallest.png"
                media="(max-width: 799px)">
        <source srcset="./images/wide-small.png"
                media="(min-width: 800px) and (max-width: 1199px)">
        <source srcset="./images/wide-default.png"
                media="(min-width: 1200px)">
        <!-- fallback for unsupported browsers -->
        <img src="./images/wide-default.png" alt="Hero Image">
    </picture>
</section>
```

## Please note:

If no navigation is required in the header, please remove the following tags from the header:
```
<input type="checkbox" id="nav-toggle" name="nav-toggle">
<label for="nav-toggle" class="nav-toggle-icon"></label>

<nav class="main-nav" role="navigation" aria-label="Main menu">
  ...
</nav>
```

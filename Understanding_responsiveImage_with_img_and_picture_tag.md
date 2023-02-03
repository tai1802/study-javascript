## 1. Images that work well on devices with widely differing screen sizes, resolutions, and other such features and look at what tools HTML provides to help implement them. This helps to improve performance across different devices.
## 2. The different responsive purposes and conventional implementation applied for each purpose:
  ### + Art direction: The problem whereby you want to serve cropped images for different layouts — for example a landscape image showing a full scene for a desktop layout, and a portrait image showing the main subject zoomed in for a mobile layout. You can solve this problem using the <picture> element.
  ### + Resolution switching: The problem whereby you want to serve smaller image files to narrow-screen devices, as they don't need huge images like desktop displays do — and to serve different resolution images to high density/low density screens. You can solve this problem using vector graphics (SVG images) and the srcset with sizes attributes.
### 3
```html
  <img 
    srcset="/img/html/vangogh-sm.jpg 240w,
            /img/html/vangogh.jpg 360w,
            /img/html/vangogh-lg.jpg 420w"
    sizes="(max-width: 880px) 240px, 
    (max-width: 1024px) 368px, 420px">
```
  #### - The srcset specifies 3 images of different size: small, medium, large. Specified sizes are 240, 360, and 420 pixels respectively. The 'w' unit indicates width (in pixels).
  #### - The srcset attribute specifies multiple images of different size or quality. Together with the sizes attribute they create responsive images that adjust according to media conditions, such as browser size. Each src in srcset has the following format: URL width

```html
  <picture>
    <source media="(max-width: 1024px)" srcset="/img/html/vangogh.jpg">
    <source media="(max-width: 880px)" srcset="/img/html/vangogh-sm.jpg">
    <img src="/img/html/vangogh-lg.jpg" alt="Vincent Van Gogh">
  </picture>
```
  #### -The <picture> element specifies multiple image sources to display. Effectively, this creates responsive images that adjust to the device details. The <picture> tag contains <source> and <img> tags. The <img> element will display when the browser does not find a proper source.

### 4
```html
<img
    srcset = "https://drberg-dam.imgix.net/product-images/electrolyte-capsules-02.png?w=200 200w,
    https://drberg-dam.imgix.net/product-images/electrolyte-capsules-02.png?w=266 266w,
    https://drberg-dam.imgix.net/product-images/electrolyte-capsules-02.png?w=310 310w,
    https://drberg-dam.imgix.net/product-images/electrolyte-capsules-02.png?w=355 355w,
    https://drberg-dam.imgix.net/product-images/electrolyte-capsules-02.png?w=400 400w,
    https://drberg-dam.imgix.net/product-images/electrolyte-capsules-02.png?w=440 440w"
    src = "https://drberg-dam.imgix.net/product-images/electrolyte-capsules-02.png"
    sizes = "(max-width: 640px) 100vw, (max-width : 1024px) 33vw, 400px"
    alt = "future product"
/>
```

# Card Hover

A small static HTML and CSS project that demonstrates an animated hover card. The card displays a Kyoto image by default, then expands on hover to reveal a title and short description.

## Project Overview

This project is built with plain HTML and CSS. It does not use JavaScript, frameworks, build tools, package managers, or external runtime dependencies. The visual interaction is handled entirely with CSS transitions and hover selectors.

The main purpose of the project is to show how a compact card can expand smoothly when the user hovers over it. The image stays visually lifted above the card while the hidden content fades and slides into view.

## Features

- Centered single-card layout.
- Pure CSS hover animation.
- Expanding card height on hover.
- Content reveal animation using `transform`, `opacity`, and `pointer-events`.
- Remote image loaded from Unsplash.
- Simple responsive base through the viewport meta tag.
- No JavaScript required.
- No installation required.

## Demo Behavior

When the page first loads:

- The browser displays a purple full-page background.
- A white card appears centered both vertically and horizontally.
- The card has a fixed width of `300px` and a collapsed height of `130px`.
- The image is shifted upward so it appears raised above the body of the card.
- The text content is hidden with `opacity: 0`.

When the card is hovered:

- The card height increases from `130px` to `250px`.
- The hidden content moves upward into view.
- The content fades in by changing opacity from `0` to `1`.
- Pointer events are enabled on the content.

## Technologies Used

- HTML5
- CSS3
- Unsplash remote image asset

## Project Structure

```text
cardHover/
+-- index.html
+-- styles.css
`-- README.md
```

## File Details

### `index.html`

The HTML file contains the page structure:

- `<!DOCTYPE html>` declares the document as HTML5.
- `<html lang="en">` sets the page language to English.
- `<meta charset="UTF-8">` enables UTF-8 character encoding.
- `<meta name="viewport" content="width=device-width, initial-scale=1.0">` improves display on mobile devices.
- `<link rel="stylesheet" href="styles.css">` connects the stylesheet.
- The body contains one `.card` element.

Main HTML elements:

```html
<div class="card">
    <div class="imgbox">
        <img src="..." alt="">
    </div>
    <div class="content">
        <h2>Kyoto</h2>
        <p>...</p>
    </div>
</div>
```

The `.card` element is the main interactive container.

The `.imgbox` element wraps the image and positions it above the card body.

The `.content` element stores the text that appears when the card is hovered.

### `styles.css`

The CSS file controls the complete design and animation.

Global reset:

```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: sans-serif;
}
```

This removes default browser spacing, uses predictable sizing, and applies a sans-serif font globally.

Body layout:

```css
body {
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background: #3A1866;
}
```

The body uses Flexbox to center the card in the viewport.

Card styling:

```css
.card {
    width: 300px;
    height: 130px;
    background: #fff;
    border-radius: 10px;
    box-shadow: 0 5px 20px rgba(0, 0, 0, .5);
    transition: .3s ease;
    padding: 30px 50px;
    cursor: pointer;
    position: relative;
}
```

The card starts compact and expands during hover. It uses a white background, rounded corners, shadow, padding, and a pointer cursor.

Image wrapper:

```css
.imgbox {
    position: relative;
    width: 100%;
    height: 100%;
    transform: translateY(-80px);
    z-index: 99;
}
```

The image wrapper is moved upward with `translateY(-80px)` and placed above other content with `z-index: 99`.

Image styling:

```css
img {
    width: 100%;
    border-radius: 10px;
    box-shadow: rgba(0, 0, 0, .5);
}
```

The image fills the available card width and matches the card's rounded corners.

Content styling:

```css
.content {
    padding: 10px;
    text-align: center;
    transform: translateY(-180px);
    transition: .2s ease-in;
    font-size: 17px;
    opacity: 0;
    pointer-events: none;
}
```

The content starts hidden and shifted upward. It is revealed only when the card is hovered.

Heading styling:

```css
.content h2 {
    color: #ee77fe;
    text-shadow:
    0 0 3px #ee77fe,
    0 0 6px #ee77fe,
    0 0 15 #ee77fe;
}
```

The heading uses a pink-purple color and glowing text shadow.

Hover content reveal:

```css
.card:hover > .content {
    transform: translateY(-140px);
    pointer-events: all;
    opacity: 1;
}
```

When the card is hovered, the content becomes visible and moves into its final position.

Hover card expansion:

```css
.card:hover {
    height: 250px;
}
```

This increases the card height and creates the expandable-card effect.

## Visual Design Details

Main colors:

- Page background: `#3A1866`
- Card background: `#fff`
- Heading color: `#ee77fe`
- Shadow color: `rgba(0, 0, 0, .5)`

Main dimensions:

- Card width: `300px`
- Initial card height: `130px`
- Hover card height: `250px`
- Card border radius: `10px`
- Card padding: `30px 50px`
- Content font size: `17px`

Animation values:

- Card transition: `.3s ease`
- Content transition: `.2s ease-in`
- Image vertical offset: `translateY(-80px)`
- Hidden content offset: `translateY(-180px)`
- Revealed content offset: `translateY(-140px)`

## How To Run

No setup is required.

1. Download or clone the project.
2. Open `index.html` in a web browser.
3. Hover over the card to see the animation.

Because this project is static, it can run directly from the file system. A local development server is optional.

## Optional Local Server

If you prefer to run it through a local server, you can use any static server.

Using Python:

```bash
python -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

## Customization Guide

### Change the Image

Update the `src` attribute in `index.html`:

```html
<img src="your-image-url.jpg" alt="Description of the image">
```

For a local image, create an image folder and reference it:

```text
assets/kyoto.jpg
```

Example:

```html
<img src="assets/kyoto.jpg" alt="Kyoto street scene">
```

### Change the Card Text

Edit the heading and paragraph inside `.content`:

```html
<h2>Kyoto</h2>
<p>Your custom description goes here.</p>
```

### Change the Background Color

Edit the `background` value in the `body` selector:

```css
background: #3A1866;
```

### Change the Card Size

Edit these values in `.card`:

```css
width: 300px;
height: 130px;
```

Also update the hover height if needed:

```css
.card:hover {
    height: 250px;
}
```

### Change the Animation Speed

Edit the transition values:

```css
transition: .3s ease;
```

and:

```css
transition: .2s ease-in;
```

Larger values make the animation slower. Smaller values make it faster.

## Browser Support

This project uses common CSS features supported by modern browsers:

- Flexbox
- CSS transitions
- CSS transforms
- Opacity
- Hover selectors
- Box shadow
- Border radius

It should work in current versions of Chrome, Edge, Firefox, Safari, and other modern browsers.

## Accessibility Notes

Current accessibility details:

- The card animation is triggered by hover, so it works best with a mouse or touchpad.
- The image currently has an empty `alt` attribute.
- There is no keyboard-specific interaction state.
- The page title is currently `Document`.

Possible accessibility improvements:

- Add descriptive image alt text.
- Rename the page title to something meaningful, such as `Card Hover`.
- Add a keyboard-friendly focus state using `:focus-within`.
- Consider supporting reduced motion with `@media (prefers-reduced-motion: reduce)`.

## Current Limitations

- The layout contains only one card.
- The card width is fixed at `300px`.
- The interaction depends on hover.
- The image is loaded from an external URL, so it requires internet access.
- There is no fallback image if the remote image fails to load.
- There is no JavaScript logic.
- There is no build process, test suite, or deployment configuration.

## Known Code Notes

- The third `text-shadow` value in `styles.css` is written as `0 0 15 #ee77fe`; CSS blur lengths normally need a unit, such as `15px`.
- The `img` selector has `box-shadow: rgba(0, 0, 0, .5);`, but `box-shadow` usually requires offset and blur values to render a visible shadow.
- The paragraph text in `index.html` contains a character encoding artifact in the contraction for `It is`.

These notes document the current project state. They can be cleaned up later without changing the main card-hover idea.

## Deployment

This project can be deployed on any static hosting service because it only contains HTML and CSS.

Common options:

- GitHub Pages
- Netlify
- Vercel
- Cloudflare Pages
- Any basic web server

The deployment root should contain:

```text
index.html
styles.css
```

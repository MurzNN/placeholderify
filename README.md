# Placeholderify CSS library

A pure CSS library that automatically transforms real HTML elements into
placeholders to simplify loading states, without requiring any JavaScript or
efforts from your side.

The classic approach requires designing separate HTML code for placeholders when
a component is in a loading state. However, this means you have to manage and
sync two versions of the element: the real one and its placeholder
representation.

This CSS library allows you to manage only one version of an HTML component -
the real HTML code. The library automatically converts the design of the real
HTML elements into a placeholder style.

All you have to do is apply the `placeholderify` CSS class to the root HTML
element of your component, and all child elements will be converted into
placeholders automatically.

## Example

Let's imagine that you have a Bootstrap Card like this:

```html
<div class="card">
  <img src="https://picsum.photos/600/400" class="card-img-top" alt="My image">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
```

And to make a placeholder from it, you should just add a CSS library and the
`placeholdify` class to the component:
```html
<link rel="stylesheet" media="all" href="//murznn.github.io/placeholderify/dist/placeholderify.min.css" />

<div class="card placeholderify" >
  <img src="https://picsum.photos/600/400" class="card-img-top" alt="My image">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
```

And that's it! 😎 No code duplication and no separate templates for
placeholders!

To restore the real component, simply remove the `placeholderify` class.

Also, the library provides a placeholder for reloading element, when you don't
need to hide the current content, for that cases include the `reloadify.css`
file and use the `reloadify` class.

For a live demonstration and customization options, check out the [example HTML
file](https://murznn.github.io/placeholderify/examples/index.html).

## Usage

The library provides several separate CSS files with different approaches:

- `placeholderify.min.css` and `placeholderify` class: a default approach which
  replaces everything inside the element by squares. And the shortened version:
  `phfy.min.css` and `phfy` class.

- `placeholderify-img.min.css` and `placeholderify-img` class: the same as
  `placeholderify` but keeps the images visible. And the shortened version:
  `phfy-i.min.css` and `phfy-i` class.

- `reloadify.min.css` and `reloadify` class: an approach for reloading elements
  with actual content. Do not hides the texts, just adds a cover and animation.
  And the shortened version:  `rlfy.min.css` and `rlfy` class.

## Customization

The library supports customization through CSS variables. Here are the available
options:

### Opacity Settings
- `--placeholderify-opacity`: Controls the opacity of placeholder elements
  (default: 0.33)

### Background and Animation
- `--placeholderify-background-color`: Sets the background color for text
  elements and images (default: currentcolor for text, black for images)
- `--placeholderify-cover-background`: Defines the gradient used for the glow
  effect (default: linear gradient from transparent to semi-transparent white)
- `--placeholderify-cover-animation-name`: The name of the animation for the
  glow effect (default: placeholderify-animation)
- `--placeholderify-cover-animation-duration`: Duration of the glow animation
  (default: 0.5s)
- `--placeholderify-cover-animation-timing-function`: Timing function for the
  glow animation (default: linear)

**Usage Example:**

```css
.my-custom-placeholder {
  --placeholderify-opacity: 0.5;
  --placeholderify-background-color: #e0e0e0;
  --placeholderify-cover-animation-duration: 1s;
}
```

### Excluding specific elements

To exclude specific elements from being transformed into placeholders, add the
`placeholderify-ignore` class to them.


### Keeping images

In some cases you probably want to keep images visible in the placeholders. To
keep only specific images visible, use the `placeholderify-ignore` class. To
make all images visible - use the `placeholderify-img.css` file and the
`placeholderify-img` class. See [example HTML file with keeping
images](https://murznn.github.io/placeholderify/examples/with-images.html).


### Shorten names

To make your HTML code more compact, the library provides shorten versions of
classes in the correspoindig CSS files:
- `placeholderify` » `phfy`
- `reloadify` » `rlfy`
- `placeholderify-img` » `phfy-i`

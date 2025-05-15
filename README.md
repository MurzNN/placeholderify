# Placeholderify CSS library

A pure CSS library that automatically transforms real HTML elements into
placeholders to simplify loading states, without requiring any JavaScript and
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
  <img src="..." class="card-img-top">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
```

And to make a placeholder from it, you should just add the `placeholdify` class:
```html
<div class="card placeholderify" >
  <img src="..." class="card-img-top">
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

For a live demonstration and customization options, check out the
[example HTML file](https://murznn.github.io/placeholderify/examples/index.html).

## Customization

The library supports customization through CSS variables. Here are the available
options:

### Opacity Settings
- `--placeholderify-opacity`: Controls the opacity of placeholder elements
  (default: 0.33)

### Background and Animation
- `--placeholderify-background-color`: Sets the background color for text elements
  and images (default: currentcolor for text, black for images)
- `--placeholderify-cover-background`: Defines the gradient used for the glow
  effect (default: linear gradient from transparent to semi-transparent white)
- `--placeholderify-cover-animation-name`: The name of the animation for the glow
  effect (default: placeholderify-animation)
- `--placeholderify-cover-animation-duration`: Duration of the glow animation
  (default: 0.5s)
- `--placeholderify-cover-animation-timing-function`: Timing function for the glow
  animation (default: linear)

### Usage Example

```css
.my-custom-placeholder {
  --placeholderify-opacity: 0.5;
  --placeholderify-background-color: #e0e0e0;
  --placeholderify-cover-animation-duration: 1s;
}
```

To exclude specific elements from being transformed into placeholders, add the
`placeholderify-ignore` class to them.

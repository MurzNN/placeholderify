# Placeholderify CSS library

A CSS library to make real HTML elements look like placeholders to simplify
making placeholders of elements when the data is loading.

The classic approach is to design a separate HTML code for placeholders for an
HTML component in the loading state. But with this approach you have to manage
and sync two versions of the element: the real one, and the placeholder
representation.

This CSS library allows you to manage only one version of an HTML component -
the real HTML code, and the library automatically converts the design of the
real HTML elements to the placeholder style.

All that you have to do is to apply the `placeholderify` CSS style to the root
HTML element of your component, and all children elements will be converted
to placeholders.

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

And that's it! 😎 No code duplication, no separate templates for placeholders!

Then, remove the `placeholdify` class and get the real component again!

See this in action in the [example HTML file](https://murznn.github.io/placeholderify/examples/index.html).

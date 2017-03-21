# Feature detection

In this project I researched some features in HTML, CSS and Javascript. My goal was to figure out what happened when features are not supported in browsers, in which browsers they don't work and how you can solve problems.

## HTML

### [1. Details element](https://frankwarnaar.github.io/minor-browser-technologies-feature-detection/features/details.html)
The details element makes it possible to make a block collapsable with plain html.

#### Syntax
```HTML
<details>
	<summary>Click me</summary>
	<p>Now you can see some more content!</p>
</details>
```

#### Support
The details element is not supported by IE, Edge and Opera Mini. Firefox has support from version 49. The element hides all the elements but the summary inside the details element. 

#### Fallback
If the browser does not support the details element, it shows all the elements. So the element has a fallback for itself.

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

Results in:
<details>
	<summary>Click me</summary>
	<p>Now you can see some more content!</p>
</details>

#### Support
The details element is not supported by IE, Edge and Opera Mini. Firefox has support from version 49. The element hides all the elements but the summary inside the details element. 

#### Fallback
If the browser does not support the details element, it shows all the elements. So the element has a fallback for itself.

### [2. Meter element](https://frankwarnaar.github.io/minor-browser-technologies-feature-detection/features/meter.html)

#### Syntax
```HTML
<p>My progress on my browser technologies is <meter low="50" high="60" max="100"
  value="48">48%</meter></p>
```

##### Attributes
1. min - The minimum value
2. max - The maximum value
3. low - The upper bound of the lower segment. Must be bigger than the min and lower than the high and max attribute.
4. high - The lower bound of the high segment. Must be smaller than the max and higher than the low and min attribute.
5. Optimum - The prefered numeric value.

Results in:
<p>My progress on my browser technologies is <meter low="50" high="60" max="100"
  value="48">48%</meter></p>
  
#### Support
The meter element is not supported by IE. It has support from Edge from version 13. iOS safari does not support the meter element.

#### Fallback
If the element is supported, the content inside the meter is not showed. Place a fallback value inside the meter element, like this:
```HTML
<p>My progress on my browser technologies is <meter low="50" high="60" max="100"
  value="48">
  	48%
</meter></p>
```

This results in the next on old browsers:

<p>My progress on my browser technologies is 48%</p>

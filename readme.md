# Feature detection

In this project I researched some features in HTML, CSS and Javascript. My goal was to figure out what happened when features are not supported in browsers, in which browsers they don't work and how you can solve problems.

## HTML

### 1. Details element
[demo](https://frankwarnaar.github.io/minor-browser-technologies-feature-detection/features/details.html)
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

### 2. Meter element
[demo](https://frankwarnaar.github.io/minor-browser-technologies-feature-detection/features/meter.html)
The meter element shows a bar that shows the progress or level of something.

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

## CSS

### 1. Columns
[Demo](https://frankwarnaar.github.io/minor-browser-technologies-feature-detection/features/columns.html)
With the columns properties, you can easily make a muli-column layout. For example, this is useful for articles.

#### Syntax
```css
article {
	// Amount of columns
	column-count: 2; 
	
	//Gutter size between columns
	column-gap: 1em;
}
```

#### Support
CSS columns are supported in all browsers, except IE < 10.

#### Fallback
Use floats as fallback for columns. This is the way I solved this:
```css
article {
		column-count: 1;
		max-width: 1080px;
		margin: 0 auto;
	}

	article p {
		max-width: 100%;
		float: left;
		box-sizing: border-box;
	}


	@media screen and (min-width: 544px) {
		article p {
			max-width: 50%;
			padding: .5em;
		}
	}


	@media screen and (min-width: 768px) {
		article p {
			max-width: 33.33%;
		}
	}

	@supports (column-count: 2 ) {
		@media screen and (min-width: 544px) {
			article {
				column-count: 2;
				column-gap: 1em;
				padding: 0;
			}

			article p {
				max-width: 100%;
			}
		}

		@media screen and (min-width: 768px) {
			article {
				column-count: 3;
			}
		}
	}
```

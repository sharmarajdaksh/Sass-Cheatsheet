Sass files use the `.scss` extention.

## Creating variables

`$variableColor : red`

### Using the variable

`background: $variableColor`

---

## Nesting elements

In Sass, nested elements are represented by nesting elements inside their parent element's brackets.

<code>header {
<br> &nbsp;
color: black;
<br> &nbsp;
button {
<br> &nbsp; &nbsp;
color: blue;
<br> &nbsp;
}
<br>
}</code>

---

## Using pseudo-selectors

To use pseudo-selectors like `:hover`, just nest them within the element's brackets with an `&:` symbol.

<code>
	button {
		<br> &nbsp; &nbsp;
		color: blue;
		<br> &nbsp; &nbsp;
		&:hover {
			color: darkblue;
		}
		<br> &nbsp;
	}
	<br>
}</code>

For selectors like `:before` and `:after`, use the `&::` symbol (double colons).

---

## Modularizing code with Sass

Say, you have a file `_header.scss` (the `_`, I believe, is for differentiating between the main file and the auxiliary files):

<code>
	<br> &nbsp;
	header {
	<br> &nbsp; &nbsp;
		// scss styles go here
	<br> &nbsp;
	}
</code>

You can import the styles to another file, using

`@import '/path/to/header'` (extension not needed)

---

## Creating mixins

Mixins are like functions which allow us to set a code block for repetitive code snippets to use wherever that code block is necessary.

<code>@mixin mixinName {
	<br/> &nbsp;
	// scss style block here
	<br/>
}</code>

Wherever you want to use the style block, say, in a div element, you can use the mixin:

<code>div {
	<br> &nbsp;
	@include mixinName();
	<br>
}</code>

Mixins are also available to be used in files which import the file where the mixin is defined.

### Using parameters in mixins

To set up parameters in scss, use the syntax:

<code>@mixin mixinName($direction) {
	<br> &nbsp;
	flex-direction: $direction;
	// remaining scss style block
	<br>
}</code>

For using the mixin, you can 'call' it with the needed parameters:

<code>div {
	<br> &nbsp;
	@include mixinName(column);
	<br>
}</code>

Multiple parameters are also usable, of course.

---

## Extensions

To inherit styles, you can extend the styles of another css selector. For example:

<code>div {
	<br> &nbsp;
	@extend .className;
	<br>
}<br></code>

The above will add to the div all the styles defined for the .className selector.

**REMEMBER** : Stylesheets work top-to-bottom. Styles defined lower will overload styles defined higher.

---

## Calculations

Calculations of all kind are possible:

`width: 100% - 20%`

`height: 100px - 50px`

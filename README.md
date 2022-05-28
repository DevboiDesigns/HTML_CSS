# HTML

- `index.html` - first page
- `! + Enter` - template doc


- [Validate HTML for Bugs](https://validator.w3.org)
- [Compare Code Checker](https://www.diffchecker.com)

## code snippets

_comment_
`< + ! + --`

### basics

- `h1` - `h6` - headers - only one h1 per page
- `<p>` - paragraph
- `<strong>` - bold
- `<em>` - italize

### lists

- `<ol>` - orderd list
- `<ul>` - un-ordered list
- `<li>` - list item

### images

- `<img src="" alt="">` - images

```html
<img
  src="./post-img.jpg"
  alt="HTML code on a screen"
  width="500"
  height="200"
/>
```

### links

**link to other websites**

- `<a href=""></a>`
- `target="_blank"` - open in new tab

```html
<a href="https://developer.mozilla.org/en-US/" target="_blank">MDN Web Docs</a>
```

**link to pages within site**

- `<a href="./blog.html">BLOG</a>`

**point at location on same page**

- `<a href="#">Challenges</a>` = `#`

### containers

_can nest within another_

- `<nav>` - container for elements of nav bar - groups
- `<header>` - group Top part of page together - with nav normally
- `<article>` - sub elements
- `<div>` - most generic container - when has no meaning
- `<aside>` - secondary info that complaments main info
- `<footer>` - bottom of page

#### html entities

- `&copy;` etc - preface with `&`

### helfpul stuff

- live server extension

# CSS

- style and layout for html
- `highlight + cmd + /` - auto comment out

**In head**

```html
<link rel="stylesheet" href="./style.css" />
```

**Style Sheet**

_Element Selector_

```css
h1 {
  color: purple;
  font-size: 26px;
  font-family: sans-serif;
  text-transform: uppercase;
  font-style: italic;
}
```

**combinig selectors**

```css
h1,
h2,
h3,
h4,
p,
li {
  font-family: sans-serif;
}
```

**child elements**

**decendent selector**

_will select child element of footer_

```css
footer p {
  font-size: 16px;
}
```

_nested elements_

```css
article header p {
  font-style: italic;
}
```

## Classes & ID Selectors

### IDs

**can only use ID names once**

**not common to use**

- `<p id="author">` on html element

_usage_

```css
#author {
  font-style: italic;
}
```

### Classes

**more common to uses classes than IDs**

- `<p class="related-author">` on html element

_usage_

```css
.related-author {
  font-size: 18px;
  font-weight: bold;
}
```

### Colors

- RGB
- values between `0` - `255`

_all values at `0` are black_

### Borders and multiple paramets

```css
aside {
  border: 5px solid #1098ad;
  /* width - style - color */

  border-top: 5px solid #1098ad;
  /* will only style top */
}
```

### Pseduo Class

- `li:`

```css
li:first-child {
  font-weight: bold;
}
```

**specifiy which child**

```css
li:nth-child(2) {
  color: red;
}
```

_all odd/ even elements_

- odd
- even

```css
li:nth-child(odd) {
  color: red;
}
```

### Styling links

- use pseudo links to get access to all states of anchors
- must be in below order
- state of element

```css
a:link {
  color: #1098ad;
  text-decoration: none; /* remove underline */
}

a:visited {
  /* display differently if clicked */
  /* color: gray; */
  color: #1098ad;
}

a:hover {
  color: orangered;
  font-weight: bold;
  text-decoration: underline orangered;
}

a:active {
  background-color: black;
  font-style: italic;
}
```

## Priority Among Selectors

**Order of priority and what code will be applied**

0. `!important` - resolve confict/ not encouraged
1. Inline Style - _dont use_
2. IDs
3. last ID
4. Class or Pseudo class
5. Element selector
6. Universal selector `*`

### Resolving Conflicts

```css
/* (1,0,0) */
#copyright {
  color: red;
}

/* (0,1,0) */
.copyright {
  color: yellow;
}

/* (0,1,0) */
.text {
  color: green;
}

/* (0,0,2) */
footer p {
  color: blue;
}
```

**imporant keyword**

_hack you should not use_

```css
footer p {
  color: blue !important;
}
```

## Inheritance

- not all properties get inherited
- mostly ones related to text

**Elements**

- `body`

```css
body {
  color: #444;
  font-family: sans-serif;
  font-size: 18px;
}
```

_overriding_

```css
h1 {
  font-size: 26px;
}
```

## Universal Selector

- `*`
- will apply changes to ALL elements
- lowest priority/ easily overriden

## Box Model

_all our optional_

- `Content` - text, images, etc
- `Border` - a line around the element, still inside of the element
- `Padding` - empty space around content, inside of elements
- `Margin` - empty space between the elements, outside of each element
- `Fill Area` - area that gets filled with background color or background image

## Short Hand

```css
.main-header {
  padding: 20px;
  padding-left: 40px;
  padding-right: 40px;
}
```

**becomes**

- 1 parameter is top/ bottom - 2 is left/ right

```css
.main-header {
  padding: 20px 40px;
}
```

## Reset Defaults

**easier to style without defaults**

```css
* {
  margin: 0;
}
```

### Center entire page

1. div container around entire body 

```css
 <body>
   <div class="container">
   /* content */
   </div>
</body>
 ```

2. style sheet 

```css
.container {
  width: 80%;
  margin: 0 auto;
}
```


## Types of Boxes

`display: block`

#### block level elements
* formatted visually as blocks
* occupy 100% of parent element width, no matter the content
* stacked vertically by default, one after another

`display: inline` 

#### inline elements
* occupies only the space neccessary
* no line-breaks
* heights and widths dont apply
* padding and margins applied ONLY horizontally (left and right)

`display: inline-block`

#### inline-block boxes
* looks like inline from the outside, behaves like block level on the inside
* occupies only contents space
* causes no line breaks

## Absolute Positioning
1. Normal Flow
  
`position: relative` 

2. Absolute 

`position: absolute`

* out of flow
* no impact on surrounding elements, might overlap
* top, bottom, left, right to offset element from its relatively positioned container

**Container Element**
```css
body {
  position: relative;
}
```

**Element**
```css
button {
  position: absolute;
  bottom: 50px;
  right: 50px;
}
```

## Pseudo Elements
* dont excist in HTML, but still can select and style in CSS

```css
h1::first-letter {
  font-style: normal;
  margin-right: 5px;
}
```

```css
p::first-line {
  color: red;
}
```

**Adjacent Selector**

* `+` to access adjacent element

```css
h3 + p::first-line {
  color: red;
}
```

**Adds element to page without html**

```css
h2::after {
  content: "TOP";
  background-color: #ffe70e;
  color: #444;
  font-size: 16px;
  font-weight: bold;
  display: inline-block;
  padding: 5px 10px;
  position: absolute;
  top: -10px;
  right: -25px;
}
```
## Layout

* `display: none;` - hide from view 

### Float Layouts 

**older method**

### Flex Box 
* set of related CSS properties
* empty space inside a container can be automatically divided by its child
* easy to align items to one another
* vertical centering - equal height columns

[Code Snippets](./Layouts/flexbox.html)

1. Flex container
2. `display: flex`
3. Flex items
   
* Main Axis ->
* Cross Axis (down)

#### Flex Container**

* `gap: 0` - length
* `justify-content: flex-start` | `center` | `space-between` | `space-around` | `space-evenly` = aligns on the *main axis* (horizontal by default)
* `align-items: stretch` | `flex-start` | `flex-end` | `center` | `baseline` = to align on the *cross axis* (vertical by default)
* `flex-direction: row` | `row-reverse` | `column` | `column-reverse` = to define which is the main axis 
* `flex-wrap: nowrap` | `wrap` | `wrap-reverse` = allow items to wrap into a new line
* `align-content: stretch` | `flex-start` | `flex-end` | `center` | `space-between` | `space-around` = *only applies when there are multiple lines* (`flex-wrap: wrap`) 

#### Flex Items

* `align-self: auto` | `stretch` | `flex-start` | `flex-end` | `center` | `baseline` = *overwrite* align-items for individual flex items
* `flex-grow: 0` | lengeth = allow an element to grow (0 means no, 1+ means yes)
* `flex-shrink: 1` | integer = allow an element to shrink (0 means no, 1+ means yes)
* `flex-basis: auto` | length = to define an items width, instead of the width property
* `flex: 0 1 auto` | int, int, len = *Recomended* shorthand for `flex-grow`, `-shrink`, `-basis`
* `order: 0` | integer = controls order of items, -1 makes them first, 1 makes it last 


### CSS Grid 
* css properties for 2D layouts
* divide container elements into rows and columns that can be filled with child elements
* 2D contexts, write less nested HTML and easier to read CSS
* works perfectly with flexbox, 1D flexbox / 2D css grid

[Code Snippets](./Layouts/css-grid.html)

#### Terminology
* `display: grid`
* grid container
* grid items
* row axis -> 
* column axis (down)
* grid lines 
* grid cell - not always seen or used 
* gutters or gaps 
* grid track (row/ column)

**usage**

*basics*

```css 
 .container--1 {
        /* CSS GRID */
        display: grid;
        grid-template-columns: 200px 200px 100px 100px;
        grid-template-rows: 300px 200px;

        /* gap: 30px; */
        column-gap: 30px;
        row-gap: 60px;
      }
```

#### Grid Container
**Establish the grid row and column tracks. One length unit for each track. Any unit can be used, new `fr` fills unusued space**
* `grid-template-rows: 'track size'`
* `grid-template-columns: 'track-size'`

**To Create empty space between tracks**
* `row-gap: 0` length
* `column-gap: 0`length 
* `gap: 0`
  
**To align items inside rows/ columns (horizontally/ vertically)**
* `justify-items: stretch` | `start` | `center` | `end`
* `align-items: stretch` | `start` | `center` | `end`

**To align entire grid inside grid container. Only applies if container is larger than the grid**
* `justify-content: start` | `start` | `center` | `end`
* `align-content: start` | `start` | `center` | `end`

#### Grid Items
**To place a grid item into a specific cell, based on line numbers. span keyword can be used to span an item across more cells**
* `grid-column: 'start-line' / 'end-line'`
* `grid-row: 'start-line' / 'end-line'`

**To overwrite justify-items / align-items for single items**
* `justify-content: stretch` | `start` | `center` | `end`
* `align-self: stretch` | `start` | `center` | `end`
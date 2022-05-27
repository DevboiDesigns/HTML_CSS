# HTML

- `index.html` - first page
- `! + Enter` - template doc

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
-

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
- lowest priority/ easily override

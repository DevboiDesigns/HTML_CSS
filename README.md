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

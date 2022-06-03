# HTML


- `! + Enter` - template doc
- [Validate HTML for Bugs](https://validator.w3.org)
- [Compare Code Checker](https://www.diffchecker.com)
- [UIFaces](https://www.uifaces.co)
- [Unsplash](https://unsplash.com)
- [Tint & Shade Generator](https://maketintsandshades.com/) - enter primary color
- [Type Scale Tool](https://type-scale.com)
- [Google Fonts](https://fonts.google.com)
- [Open Colors](https://yeun.github.io/open-color/)
- [Icons: Iconic](https://ionic.io/ionicons)
- [Icons: Hero](https://heroicons.com)
- [Coolers](https://coolors.co/) - all things color & more / color scheme generator 
- [Contrast Checker](https://coolors.co/contrast-checker/112a46-acc8e5)

## code snippets

* `&nbsp;` - space for desining/ placeholder

_comment_
`< + ! + --`

### basics

- `h1` - `h6` - headers - only one h1 per page
- `<p>` - paragraph
- `<strong>` - bold
- `<em>` - italize
- `<table>` - `<tr>` - `<td>` - table
- `<thead>` - table head
- `<tbody>` - table body
- `<th>` - table row header
- `<figure>`
- `<menu>` - Menu buttons in web app - not as common
    
[Hero Project](./Components/05-hero.html)
```html
<body>
    <header>
      <nav>
        <div>LOGO</div>
        <div>Navigation</div>
      </nav>
    </header>
    <section>

    </section>
  </body>
```

[App Layout Project](./Components/06-app-layout.html)
```html
 <body>
    <!-- Contains links that point to other parts of website -->
    <nav>Nav</nav>
    <!-- Menu buttons in web app -->
    <menu>Menu</menu>
    <section>Inbox</section>
    <main>Email view</main>
    <aside>Additional Info</aside>
  </body>
```
      
    

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

* `<blockquote>` - qoute syntax

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

- `&copy;` etc - preface with `&` = copyright symbol
- `&mdash` = dash line `-`

### helfpul stuff

- live server extension

### Units of measurment
* rem - default 16px unless set 
* max-width - will adjust to viewport 
* vh - viewport height e.g. `100vh` = 100% of viewport height
* vw
* % - percentage of parent element
* px - pixels - not advised to use 

```css
html {
  /* SETS default REM to 10px and allows users to change font sizes */
  font-size: 62.5%;
}
```

# Fonts 

* add fonts to head sectio in `link`

```html
 <link
      href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;700&family=Raleway:wght@100&display=swap"
      rel="stylesheet"
    />
```

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

**generally just have a class for every element, best practice, scalable**

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

#### Flex Container

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

**Extra**
* `left: 0` - to align left 
* `right: 0` - to align right 


### CSS Grid 
* css properties for 2D layouts
* divide container elements into rows and columns that can be filled with child elements
* 2D contexts, write less nested HTML and easier to read CSS
* works perfectly with flexbox, 1D flexbox / 2D css grid

[Code Snippets](./Layouts/css-grid.html)

* nothing wrong with just using CSS grid for everything

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


# Web Design Rules
[Design Rules](all-design-guidelines.pdf)

## Typography
* [Type Scale Tool](https://type-scale.com)
* [Google Fonts](https://fonts.google.com)
* use only popular/ good
* ok to use only one typeface per site
* choose accordingly to **site

  ### serif 
  * tails at end of lines
  * creates a traditional/ classic look and feel
  * conveys trustworthiness
  * good for long text

  *examples*
  * merriweather
  * aleo
  * playfair display
  * cormorant
  * cardo
  * lora

  ### sans-serif 
  * clean and simple (no tails)
  * modern look and feel
  * easier to choose for beginner

  *examples*
  * inter
  * open sans
  * roboto
  * montserrat
  * work sans
  * lato

### Size
* normal text - `16px-32px`
* long text/ blog post - `20px-or bigger`
* headlines - `50px+` and `bold-600px+`
* for any text - DONT use a font weight under 400 (regular)

### Font-weight
* 400 - regular
* 500 - medium
* 700 - bold 

### Tips/ Tricks
* use less than 75 characters per line (width)
* normal text line height `1.5-2` Big text - `below 1.5`
* the smaller or longer the text, the *Larger* the line height needs to be
* if looks unnatural - decrease letter spacing
* experiment with all caps for short titles, make small and bold and increase letter spacing
* usually dont justify text - dont center side to side (better to align to left)
* `Lorem` typing this will generate random text 


### Scale Tool

```css
/*
SPACING SYSTEM (px)
2 / 4 / 8 / 12 / 16 / 24 / 32 / 48 / 64 / 80 / 96 / 128

FONT SIZE SYSTEM (px)
10 / 12 / 14 / 16 / 18 / 20 / 24 / 30 / 36 / 44 / 52 / 62 / 74 / 86 / 98
*/
```

## Colors

* [Open Colors](https://yeun.github.io/open-color/)
* open source color pallet for UI 

## Images/ Illustrations

## Icons

* [Icons](https://heroicons.com)
* designed ideal at `width: 24px;`


**add as html element**

```html
<svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
  <path stroke-linecap="round" stroke-linejoin="round" d="M19 9l-7 7-7-7" />
</svg>
```

## Shadows

## Border-radius

## Whitespace

## Visual Hierarchy

## User Experience

## Components/ Layout

# Website Personalities 

## Serious/ Elegant
* for luxury and elegance, based on thin serif typefaces, golden or pastel colors, and big high quality images

## Minimalist/ Simple
* focuses on the essential text content, using small or medium sized sans-serif black text, lines, and few images and icons

## Plain/ Neutral
* design that gets out of the way by using neutral and small typefaces, and a very strutured layout. Common in big corporations

## Bold/ Confident
* makes an impact, by featuring big and bold typography, paired with confident use of big and bright colored blocks

## Calm/ Peacful
* for products and services that care, transmitted by calming pastel colors, soft serif headings, and  matching images/ illustrations

## Startup/ Upbeat
* widely used in startups, featuring medium-sized sans-serif typefaces, light-grey text and backgrounds, and rounded elements

## Playful/ Fun
* colorful and round designs, fueled by creative elements like hand-drawn icons or illustrations, animations, and fun language



# Elements & Components 
* Elements -> Components -> Layouts -> Webpage
* use common elements and components to convey your website's information
* combine components into layouts using common layout patterns
* assemble different layout areas into a complete, final page 
  
1. Elements
  - Text
  - Buttons
  - Images
  - Input Elements
  - Tags

2. Components
   - Breadcrumbs
   - [Pagination](./Components/04-pagination.html)
   - Alert and status bars
   - Statistics
   - Gallery
   - Feature Box
   - Preview and profile cards
   - [Accordion](/Components/01-accordion.html)
   - Tabs
   - [Carousel](./Components/02-carousel.html)
   - Customer testimonals
   - Customer logos
   - Featured-in logos
   - Steps
   - Forms
   - [Tables](./Components/03-table.html)
   - Pricing tables
   - Modal windows

3. Section Components
   - Navigation 
   - [Hero Section](./Components/05-hero.html) 
   - Footer
   - Call-to-action section
   - Feature row

4. Layout Patterns
   - Row of boxes or cards
   - [Grid of boxes or cards](./Components/06-app-layout.html)
   - Z-pattern
   - F-pattern
   - Single Column
   - Sidebar
   - Multi-column/ magazine
   - Asymmetry/ Experimental


# Responive Design 
* must be set from the very beginning 
* design technique to make website adjust its layout and visual style to any possible screen size (window or viewport)
* makes usable on all devices - desktops, tablets, phones
* set of best practices, not a seperate technology 

## Design Ingredients 
* Fluid Layouts
   - allow webpage to adapt to current viewport width (or even height)
   - use % (or vh / vw) unit instead of px for elements that should adapt to viewport (usually layout)
   - use max-width instead of width
  
* Responive Units
  - use rem unit instead of px for most lengths 
  - to make it easy to scale the entire layout down (or up) automatically
  - helpful trick: setting 1rem to 10px for easy calculations

* Flexible Images
  - by default, images do not scale to the viewport 
  - always use % for image dimensions, together with the max-width property 
  
* Media Queries
  - to change CSS styles on certain viewport widths (different widths on different devices) (called breakpoints)

**start with Desktop design then use media queries to shrink design to smaller screens**

**more modern approaches work from Mobile First design then scale up to desktop**


# Designing A Complete Website
## 7 Steps
1. [Define](#define)
2. [Plan](#plan)
3. [Sketch](#sketch)
4. [Design & Build](#design--build)
5. [Test & Optimize](#test--optimize)
6. [Launch](#launch)
7. [Maintain & Update](#maintain--update) 

### Define
* Who is the website for?  
* What is the website for? - what is the purpose 
  1. Providing information
  2. Selling something
  3. Entertaining
* Define a target audience - be very specific if possible

### Plan
* gather website content - text, images, videos
* free images or provided by client
* bigger sites: plan sitemap - what pages site needs, and how related to each other (content heirarchy)
* plan what sections each page needs in order to convey the contents message
* [define website personality](#website-personalities)

### Sketch
* think about what components you need and how you can use them in layout patterns
* get ideas out of your head: sketch with pen and paper or with design software 
* this is an iterative process: experiment with different components and layouts 
* dont sketch everything or perfect 
* jump between code & sketches 

### Design & Build
* use decisions, content, and sketches - design in browser for testing & prototyping 
* design layout and components from sketch - design actual visual styles
* create design based off selected website personality, design guidelines & inspiration
* use clients branding for design decisions when you can 

### Test & Optimize
* make sure works in all major browers (chrome, firefox, safari, edge)
* test on actual mobile devices, not just in dev tools
* optimize all images, dimension & file size - compress
* fix simple accesiblity problems (e.g. color contrast issues)
* run the [Lighthouse](https://chrome.google.com/webstore/detail/lighthouse/blipmdconlkpinefehnmjammfjpmpbjk?hl=en) performance test in Chrome DevTools and try to fix reported issues
* think about Search Engine Optimization (SEO)

### Launch
* once its all perfect - Launch 
* upload to hosting platform (countless platforms: e.g. [Netlify](https://www.netlify.com))
* choose and buy a Domain Name -memorable and easy to write 

### Maintain & Update
* keep the webiste content updated over time -if for client, monthly maintenance contract 
* install analytics software such as [Google Analytics](https://analytics.google.com/analytics/web/#/p294168974/reports/intelligenthome) or [Fathom](https://usefathom.com) - may inform you of user information to make future changes in the site structure and content
* a blog that is updated regularly is a good way to keep users coming back, and is also good for SEO

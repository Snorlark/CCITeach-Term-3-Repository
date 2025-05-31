# CSS3 Cheatsheet

## Selectors
```css
/* Element */
div { }

/* Class */
.class { }

/* ID */
#id { }

/* Descendant */
div p { }

/* Child */
div > p { }

/* Adjacent Sibling */
div + p { }

/* General Sibling */
div ~ p { }

/* Attribute */
[type="text"] { }
[class*="btn"] { }
[href^="https"] { }
[href$=".pdf"] { }

/* Pseudo-classes */
:hover { }
:focus { }
:active { }
:first-child { }
:last-child { }
:nth-child(n) { }
:not(selector) { }

/* Pseudo-elements */
::before { }
::after { }
::first-line { }
::first-letter { }
```

## Box Model
```css
/* Box Sizing */
box-sizing: border-box;
box-sizing: content-box;

/* Dimensions */
width: 100px;
height: 100px;
min-width: 100px;
max-width: 100px;
min-height: 100px;
max-height: 100px;

/* Margins */
margin: 10px;
margin: 10px 20px;
margin: 10px 20px 30px 40px;
margin-top: 10px;
margin-right: 10px;
margin-bottom: 10px;
margin-left: 10px;

/* Padding */
padding: 10px;
padding: 10px 20px;
padding: 10px 20px 30px 40px;
padding-top: 10px;
padding-right: 10px;
padding-bottom: 10px;
padding-left: 10px;

/* Border */
border: 1px solid black;
border-width: 1px;
border-style: solid;
border-color: black;
border-radius: 5px;
```

## Display & Positioning
```css
/* Display */
display: block;
display: inline;
display: inline-block;
display: none;
display: flex;
display: grid;

/* Position */
position: static;
position: relative;
position: absolute;
position: fixed;
position: sticky;

/* Z-index */
z-index: 1;

/* Float */
float: left;
float: right;
float: none;
clear: both;
```

## Flexbox
```css
/* Container */
display: flex;
flex-direction: row;
flex-wrap: wrap;
flex-flow: row wrap;
justify-content: flex-start;
align-items: stretch;
align-content: flex-start;
gap: 10px;

/* Items */
flex-grow: 0;
flex-shrink: 1;
flex-basis: auto;
flex: 0 1 auto;
align-self: auto;
order: 0;
```

## Grid
```css
/* Container */
display: grid;
grid-template-columns: repeat(3, 1fr);
grid-template-rows: auto;
grid-template-areas: "header header header"
                     "sidebar main main"
                     "footer footer footer";
gap: 10px;
justify-items: stretch;
align-items: stretch;

/* Items */
grid-column: 1 / 3;
grid-row: 1 / 2;
grid-area: header;
justify-self: stretch;
align-self: stretch;
```

## Typography
```css
/* Font Family */
font-family: Arial, sans-serif;

/* Font Size */
font-size: 16px;
font-size: 1rem;
font-size: 100%;

/* Font Weight */
font-weight: normal;
font-weight: bold;
font-weight: 400;

/* Font Style */
font-style: normal;
font-style: italic;

/* Line Height */
line-height: 1.5;
line-height: 150%;

/* Text Align */
text-align: left;
text-align: center;
text-align: right;
text-align: justify;

/* Text Decoration */
text-decoration: none;
text-decoration: underline;
text-decoration: line-through;

/* Text Transform */
text-transform: none;
text-transform: uppercase;
text-transform: lowercase;
text-transform: capitalize;

/* Letter Spacing */
letter-spacing: 1px;

/* Word Spacing */
word-spacing: 2px;
```

## Colors & Backgrounds
```css
/* Colors */
color: #ff0000;
color: rgb(255, 0, 0);
color: rgba(255, 0, 0, 0.5);
color: hsl(0, 100%, 50%);
color: hsla(0, 100%, 50%, 0.5);

/* Background */
background-color: #fff;
background-image: url('image.jpg');
background-repeat: no-repeat;
background-position: center;
background-size: cover;
background-attachment: fixed;
```

## Transitions & Animations
```css
/* Transitions */
transition: all 0.3s ease;
transition-property: width;
transition-duration: 0.3s;
transition-timing-function: ease;
transition-delay: 0s;

/* Animations */
@keyframes slide {
    from { transform: translateX(0); }
    to { transform: translateX(100px); }
}
animation: slide 1s ease infinite;
animation-name: slide;
animation-duration: 1s;
animation-timing-function: ease;
animation-delay: 0s;
animation-iteration-count: infinite;
animation-direction: normal;
animation-fill-mode: none;
```

## Media Queries
```css
/* Breakpoints */
@media (max-width: 768px) { }
@media (min-width: 768px) { }
@media (min-width: 768px) and (max-width: 1024px) { }

/* Device Orientation */
@media (orientation: portrait) { }
@media (orientation: landscape) { }

/* Print */
@media print { }

/* Resolution */
@media (min-resolution: 192dpi) { }
```

## Transform & Filters
```css
/* Transform */
transform: translate(10px, 20px);
transform: rotate(45deg);
transform: scale(1.5);
transform: skew(10deg);
transform: matrix(1, 0, 0, 1, 10, 20);

/* Filters */
filter: blur(5px);
filter: brightness(150%);
filter: contrast(200%);
filter: grayscale(100%);
filter: sepia(100%);
filter: hue-rotate(90deg);
filter: invert(100%);
filter: opacity(50%);
filter: saturate(200%);
```

## Variables
```css
:root {
    --primary-color: #007bff;
    --secondary-color: #6c757d;
    --font-size: 16px;
    --spacing: 1rem;
}

.element {
    color: var(--primary-color);
    font-size: var(--font-size);
    margin: var(--spacing);
}
```

## Common Units
```css
/* Absolute */
px      /* Pixels */
pt      /* Points */
cm      /* Centimeters */
mm      /* Millimeters */
in      /* Inches */

/* Relative */
%       /* Percentage */
em      /* Relative to font-size */
rem     /* Relative to root font-size */
vw      /* Viewport width */
vh      /* Viewport height */
vmin    /* Minimum viewport dimension */
vmax    /* Maximum viewport dimension */
```

## Best Practices
1. Use CSS reset or normalize
2. Follow BEM naming convention
3. Use CSS variables for theming
4. Implement mobile-first design
5. Optimize selectors
6. Minimize specificity
7. Use shorthand properties
8. Group related properties
9. Comment complex rules
10. Use appropriate units

## Common Layout Patterns
```css
/* Centering */
.center {
    display: flex;
    justify-content: center;
    align-items: center;
}

/* Sticky Footer */
.sticky-footer {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
}
.sticky-footer main {
    flex: 1;
}

/* Two Column Layout */
.two-column {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
}

/* Card Layout */
.card {
    display: flex;
    flex-direction: column;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}
```

## Common Utility Classes
```css
/* Spacing */
.m-0 { margin: 0; }
.m-1 { margin: 0.25rem; }
.m-2 { margin: 0.5rem; }
.m-3 { margin: 1rem; }

.p-0 { padding: 0; }
.p-1 { padding: 0.25rem; }
.p-2 { padding: 0.5rem; }
.p-3 { padding: 1rem; }

/* Text */
.text-center { text-align: center; }
.text-left { text-align: left; }
.text-right { text-align: right; }

.text-bold { font-weight: bold; }
.text-italic { font-style: italic; }

/* Display */
.d-none { display: none; }
.d-block { display: block; }
.d-flex { display: flex; }
.d-grid { display: grid; }

/* Flex */
.flex-row { flex-direction: row; }
.flex-column { flex-direction: column; }
.justify-center { justify-content: center; }
.align-center { align-items: center; }
```

## Common Media Query Breakpoints
```css
/* Mobile First */
/* Small devices (phones) */
@media (min-width: 576px) { }

/* Medium devices (tablets) */
@media (min-width: 768px) { }

/* Large devices (desktops) */
@media (min-width: 992px) { }

/* Extra large devices */
@media (min-width: 1200px) { }

/* Common device breakpoints */
/* iPhone SE */
@media (max-width: 375px) { }

/* iPhone X/11 */
@media (max-width: 414px) { }

/* iPad */
@media (max-width: 768px) { }

/* iPad Pro */
@media (max-width: 1024px) { }

/* Desktop */
@media (max-width: 1440px) { }
``` 
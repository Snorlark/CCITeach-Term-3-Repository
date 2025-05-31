# HTML5 Cheatsheet

## Document Structure
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <!-- Content goes here -->
</body>
</html>
```

## Semantic Elements
```html
<header>    <!-- Site header -->
<nav>       <!-- Navigation -->
<main>      <!-- Main content -->
<article>   <!-- Self-contained content -->
<section>   <!-- Thematic grouping -->
<aside>     <!-- Sidebar content -->
<footer>    <!-- Site footer -->
```

## Text Elements
```html
<h1> to <h6>    <!-- Headings -->
<p>             <!-- Paragraph -->
<strong>        <!-- Important text -->
<em>            <!-- Emphasized text -->
<mark>          <!-- Highlighted text -->
<small>         <!-- Small text -->
<del>           <!-- Deleted text -->
<ins>           <!-- Inserted text -->
<sub>           <!-- Subscript -->
<sup>           <!-- Superscript -->
```

## Lists
```html
<ul>            <!-- Unordered list -->
<ol>            <!-- Ordered list -->
<li>            <!-- List item -->
<dl>            <!-- Description list -->
<dt>            <!-- Description term -->
<dd>            <!-- Description details -->
```

## Links and Media
```html
<a href="url">      <!-- Hyperlink -->
<img src="url">     <!-- Image -->
<figure>            <!-- Figure container -->
<figcaption>        <!-- Figure caption -->
<video>             <!-- Video player -->
<audio>             <!-- Audio player -->
<iframe>            <!-- Inline frame -->
```

## Forms
```html
<form>              <!-- Form container -->
<input type="text"> <!-- Text input -->
<input type="email"><!-- Email input -->
<input type="password"><!-- Password input -->
<input type="number"><!-- Number input -->
<input type="date"> <!-- Date input -->
<input type="checkbox"><!-- Checkbox -->
<input type="radio"> <!-- Radio button -->
<select>            <!-- Dropdown list -->
<option>            <!-- Dropdown option -->
<textarea>          <!-- Text area -->
<button>            <!-- Button -->
<label>             <!-- Form label -->
```

## Tables
```html
<table>             <!-- Table container -->
<thead>             <!-- Table header -->
<tbody>             <!-- Table body -->
<tfoot>             <!-- Table footer -->
<tr>                <!-- Table row -->
<th>                <!-- Table header cell -->
<td>                <!-- Table data cell -->
<caption>           <!-- Table caption -->
```

## Meta Tags
```html
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="description" content="Page description">
<meta name="keywords" content="keywords, for, search">
<meta name="author" content="Author name">
<meta name="robots" content="index, follow">
```

## Common Attributes
```html
class="..."         <!-- CSS class -->
id="..."            <!-- Unique identifier -->
style="..."         <!-- Inline styles -->
title="..."         <!-- Tooltip text -->
alt="..."           <!-- Image alt text -->
href="..."          <!-- Link URL -->
src="..."           <!-- Source URL -->
type="..."          <!-- Input type -->
name="..."          <!-- Form field name -->
value="..."         <!-- Form field value -->
placeholder="..."   <!-- Input placeholder -->
required            <!-- Required field -->
disabled            <!-- Disabled element -->
```

## HTML5 APIs
```html
<!-- Geolocation -->
navigator.geolocation

<!-- Local Storage -->
localStorage.setItem()
localStorage.getItem()

<!-- Web Workers -->
new Worker()

<!-- WebSocket -->
new WebSocket()

<!-- Canvas -->
<canvas>

<!-- SVG -->
<svg>
```

## Best Practices
1. Use semantic HTML elements
2. Include proper meta tags
3. Add alt text to images
4. Use proper heading hierarchy
5. Validate HTML code
6. Ensure accessibility
7. Optimize for SEO
8. Keep code clean and organized

## Common Character Entities
```html
&nbsp;     <!-- Non-breaking space -->
&lt;        <!-- Less than -->
&gt;        <!-- Greater than -->
&amp;       <!-- Ampersand -->
&copy;      <!-- Copyright -->
&reg;       <!-- Registered trademark -->
&trade;     <!-- Trademark -->
&deg;       <!-- Degree -->
&euro;      <!-- Euro -->
&pound;     <!-- Pound -->
```

## Accessibility Attributes
```html
role="..."          <!-- ARIA role -->
aria-label="..."    <!-- ARIA label -->
aria-hidden="true"  <!-- Hide from screen readers -->
tabindex="0"        <!-- Make focusable -->
alt="..."           <!-- Image description -->
title="..."         <!-- Tooltip text -->
```

## Common Input Types
```html
text        <!-- Text input -->
email       <!-- Email input -->
password    <!-- Password input -->
number      <!-- Number input -->
tel         <!-- Telephone input -->
url         <!-- URL input -->
date        <!-- Date input -->
time        <!-- Time input -->
datetime-local <!-- Date and time -->
month       <!-- Month input -->
week        <!-- Week input -->
color       <!-- Color picker -->
range       <!-- Range slider -->
file        <!-- File upload -->
submit      <!-- Submit button -->
reset       <!-- Reset button -->
button      <!-- Generic button -->
```

## Form Validation Attributes
```html
required            <!-- Required field -->
minlength="n"       <!-- Minimum length -->
maxlength="n"       <!-- Maximum length -->
min="n"             <!-- Minimum value -->
max="n"             <!-- Maximum value -->
pattern="regex"     <!-- Pattern matching -->
multiple            <!-- Multiple values -->
accept="type"       <!-- Accepted file types -->
```

## Common Meta Tags for SEO
```html
<meta name="description" content="...">
<meta name="keywords" content="...">
<meta name="author" content="...">
<meta name="robots" content="index, follow">
<meta property="og:title" content="...">
<meta property="og:description" content="...">
<meta property="og:image" content="...">
<meta name="twitter:card" content="summary">
```

## Common Viewport Meta Tags
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0">
<meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
```

## Common Favicon Links
```html
<link rel="icon" type="image/x-icon" href="/favicon.ico">
<link rel="apple-touch-icon" href="/apple-touch-icon.png">
<link rel="manifest" href="/manifest.json">
```

## Common CSS Links
```html
<link rel="stylesheet" href="style.css">
<link rel="stylesheet" href="print.css" media="print">
<link rel="stylesheet" href="mobile.css" media="(max-width: 768px)">
```

## Common JavaScript
```html
<script src="script.js"></script>
<script src="script.js" defer></script>
<script src="script.js" async></script>
<script type="module" src="module.js"></script>
``` 
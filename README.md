# Steller CSS

![CircleCI branch](https://img.shields.io/circleci/project/github/tjhillard/steller-css/master.svg)
[![npm version](https://badge.fury.io/js/steller-css.svg)](https://badge.fury.io/js/steller-css)
![npm](https://img.shields.io/npm/dt/steller-css.svg)
![NPM](https://img.shields.io/npm/l/steller-css.svg)

Steller is a utility-first CSS framework that serves as the foundation of your application's design system. It includes built-in smart defaults for building responsive, accesible, and visually consistent user interfaces. Unlike other CSS frameworks, Steller has no opinion on the actual end appearance of your application, it is simply a bridge for your design system and your application's styling.

>Open-source development of Steller is proudly sponsored by [Snap! Raise](https://www.snap-raise.com/).

## Features
* Simple configuration & setup ⚙️
* Grid system built with CSS Grid 📏
* Sass based ✨
* Encourages mobile-first development 📱
* Built-in responsive typography ✍️
* Extensible module system 🚀
* Zero dependencies 🙌

## Installation

```
npm i steller-css
```

```
yarn add steller-css
```

## Usage

1. Create a `theme.scss` (or any name you prefer)
2. Copy pasta the values in the [example config](https://github.com/tjhillard/steller-css/blob/master/src/example-theme.scss)
3. Adjust the theme variables to your design system's needs.
4. In your `index.scss` or equivilent, import your newly created `theme.scss` at the top of your entry point sass file
5. Import steller from node_modules
```scss
// Assuming you are using webpack

@import 'steller-theme'; // Your config file
@import '~steller-css/index'; // StellerCSS
```

## Example Projects

* [Steller + Vue CLI 3 | Codesandbox](https://codesandbox.io/s/qlpqoloq5j?fontsize=14)
* [Steller + Nuxt.js | GitHub](https://github.com/tjhillard/tjhillard.com)

## Config

All config variables are optional to define as they already have default values. [You can take a look at them here](https://github.com/tjhillard/steller-css/blob/master/src/defaults.scss).

### Colors

```scss
$steller-colors: (
  // brand
  'primary': #586f7c,
  'secondary': #b8dbd9,

  // accents
  'dwight-schrute': #0FF1C3,
  'a-song-of-this-and-fire': #1CE,
);
```

### Typogrpahy

```scss
$steller-font-family-heading: 'Some trendy web font', sans-serif;
$steller-font-family-body: 'Comic Sans', sans-serif;

$steller-custom-font-families: (
  'accent': cursive,
);

$steller-font-size-xs: 0.75rem;
$steller-font-size-sm: 0.875rem;
$steller-font-size-md: 1rem;
$steller-font-size-lg: 1.5rem;
$steller-font-size-xl: 1.875rem;
$steller-font-size-2xl: 2.25rem;
$steller-font-size-3xl: 3rem;
$steller-font-size-4xl: 3.75rem;

$steller-font-weight-bold: 700;
$steller-font-weight-medium: 500;
$steller-font-weight-regular: 400;
$steller-font-weight-light: 300;
$steller-font-weight-thin: 100;

$steller-leading-sm: 1.25em;
$steller-leading-md: 1.5em;
$steller-leading-lg: 2em;

$steller-letter-spacing-tight: -0.05em;
$steller-letter-spacing-normal: 0em;
$steller-letter-spacing-wide: 0.05em;
```

### Breakpoints

```scss
$steller-breakpoint-sm: 380px;
$steller-breakpoint-md: 600px;
$steller-breakpoint-lg: 980px;
```

### Container

```scss
$steller-container-width: 1140px;
```

### Grid

```scss
$steller-grid-columns: 12;

$steller-column-gutter-sm: 16px;
$steller-column-gutter-md: 16px;
$steller-column-gutter-lg: 24px;

$steller-row-gutter-sm: 8px;
$steller-row-gutter-md: 8px;
$steller-row-gutter-lg: 16px;
```

### Spacing

```scss
$steller-spacing-xs: 4px;
$steller-spacing-sm: 8px;
$steller-spacing-md: 16px;
$steller-spacing-lg: 24px;
$steller-spacing-xl: 32px;
$steller-spacing-2xl: 48px;
$steller-spacing-3xl: 64px;
```

### Borders

```scss
$steller-border-radius-sm: 5px;
$steller-border-radius-md: 10px;
$steller-border-radius-lg: 15px;
$steller-border-radius-xl: 20px;

$steller-border-width-xs: 1px;
$steller-border-width-sm: 2px;
$steller-border-width-md: 4px;
$steller-border-width-lg: 6px;
$steller-border-width-xl: 8px;
```

### Motion

```scss
$steller-speed-extra-slow: 500ms;
$steller-speed-slow: 400ms;
$steller-speed-normal: 300ms;
$steller-speed-fast: 200ms;
$steller-speed-extra-fast: 100ms;
```

### Effects

```scss
$steller-box-shadow-sm: 0 7px 15px 0 rgba(0, 0, 0, 0.11), 0 1px 8px 0 rgba(0, 0, 0, 0.06);
$steller-box-shadow-md: 0 10px 20px 0 rgba(0, 0, 0, 0.22), 0 3px 12px 0 rgba(0, 0, 0, 0.07);
$steller-box-shadow-lg: 0 15px 30px 0 rgba(0, 0, 0, 0.33), 0 5px 15px 0 rgba(0, 0, 0, 0.1);
```

### Gradients

```scss
$steller-gradients: (
  'cta-primary': linear-gradient(to right, #55c1ff, #5863f8),
);
```

## Utility Classes

### Container
| Class | Properties |
| --- | --- |
| .container | margin: 0 auto; max-width: $container-width; position: relative; |

```html
<div class="container"></div>
```

### Grid

| Class | Properties |
| --- | --- |
| .grid | display: grid; grid-template-columns: repeat($grid-columns, 1fr); |
| .{$breakpont}:col-{$span} | grid-column: span $span; |
| .{$breakpont}:row-{$span} | grid-row: span $span; |
| .{$breakpont}:col-{$span}-start-{$grid-column-start} | grid-column: $grid-column-start / span $span; |

```html
<div class="grid">
  <div class="col-12 md:col-6"></div>
  <div class="col-12 md:col-6"></div>
</div>
```

### Typography

| Class | Properties |
| --- | --- |
| .font-size-{$size} | font-size: $size |
| .font-weight-{$weight} | font-size: $weight |
| .leading-{$leading} | line-height: $leading |
| .italic | font-style: italic; |
| .underline | text-decoration: underline; |
| .no-underline | text-decoration: none; |
| .lowercase | text-transform: lowercase; |
| .uppercase | text-transform: uppercase; |
| .capitalize | text-transform: captialize; |
| .letter-spacing-tight | letter-spacing: -0.05em; |
| .letter-spacing-normal | letter-spacing: 0em; |
| .letter-spacing-wide | letter-spacing: 0.05em; |
| .list-reset | list-style: none; padding: 0; |
| .whitespace-normal | white-space: normal; |
| .whitespace-no-wrap | white-space: nowrap; |
| .whitespace-pre | white-space: pre; |
| .whitespace-pre-line | white-space: pre-line; |
| .whitespace-pre-wrap | white-space: pre-wrap; |
| .break-word | word-wrap: break-word; |
| .break-word | word-wrap: normal; |
| .truncate | overflow: hidden; text-overflow: ellipses; white-space: nowrap; |

```html
<!-- font size -->
<div class="font-size-3xl"></div>

<!-- font weight -->
<div class="font-weight-bold"></div>

<!-- leading (line height) -->
<div class="leading-sm"></div>
```

### Color

| Class | Properties |
| --- | --- |
| .text-{$color} | color: $color; |
| .bg-{$color} | background-color: $color; |

```scss
$steller-colors: (
  'my-color-name': #586f7c,
);
```
```html
<div class="text-my-color-name"></div>
<div class="bg-my-color-name"></div>
```

### Layout

| Class | Properties |
| --- | --- |
| .block | display: block; |
| .inline-block | display: inline-block; |
| .inline | display: inline; |
| .hidden | display: none; |
| .text-center | text-align: center; |
| .text-left | text-align: left; |
| .text-right | text-align: right; |
| .text-justify | text-align: justify; |
| .float-left | float: left; |
| .float-right | float: right; |
| .float-none | float: none; |
| .static | position: static; |
| .fixed | position: fixed; |
| .absolute | position: absolute; |
| .relative | position: relative; |
| .sticky | position: sticky; |
| .pin | top: 0; right: 0; bottom: 0; left: 0; |
| .pin-t | top: 0; |
| .pin-r | right: 0; |
| .pin-b | bottom: 0; |
| .pib-l | left: 0; |
| .visible | visibility: visible; |
| .invisible | visibility: hidden; |
| .z-0 | z-index: 0; |
| .z-1 | z-index: 1; |
| .z-2 | z-index: 2; |
| .z-10 | z-index: 10; |
| .z-20 | z-index: 20; |
| .z-max | z-index: 2147483647; |
| .vertical-align-baseline | vertical-align: baseline; |
| .vertical-align-top | vertical-align: top; |
| .vertical-align-middle | vertical-align: middle; |
| .vertical-align-bottom | vertical-align: bottom; |
| .vertical-align-text-top | vertical-align: text-top; |
| .vertical-align-text-bottom | vertical-align: text-bottom; |

### Spacing

| Class | Properties |
| --- | --- |
| .m-{$size} | margin: $size; |
| .p-{$size} | padding: $size; |
| .mx-{$size} | margin-left: $size; margin-right: $size; |
| .px-{$size} | padding-left: $size; padding-right: $size; |
| .my-{$size} | margin-top: $size; margin-bottom: $size; |
| .py-{$size} | padding-top: $size; padding-bottom: $size; |
| .mt-{$size} | margin-top: $size; |
| .pt-{$size} | padding-top: $size; |
| .mr-{$size} | margin-right: $size; |
| .pr-{$size} | padding-right: $size; |
| .mb-{$size} | margin-bottom: $size; |
| .pb-{$size} | padding-bottom: $size; |
| .ml-{$size} | margin-left: $size; |
| .pl-{$size} | padding-left: $size; |

* Spacing Sizes: ('xs', 'sm', 'md', 'lg', 'xl', '2xl', '3xl')

```html
<!-- margin all sides large -->
<div class="m-lg"></div>

<!-- padding top/bottom small -->
<div class="py-sm"></div>

<!-- margin top 2xl -->
<div class="mt-2xl"></div>

<!-- padding right extra small -->
<div class="pr-xs"></div>
```

### Flexbox

| Class | Properties |
| --- | --- |
| .flex | display: flex; |
| .inline-flex | display: inline-flex; |
| .flex-row | flex-direction: row; |
| .flex-col | flex-direction: col; |
| .flex-row-reverse | flex-direction: row-reverse; |
| .flex-col-reverse | flex-direction: col-reverse; |
| .flex-wrap | flex-wrap: wrap; |
| .flex-no-wrap | flex-wrap: nowrap; |
| .flex-wrap-reverse | flex-wrap: wrap-reverse; |
| .items-strech | align-items: stretch; |
| .items-start | align-items: flex-start; |
| .items-center | align-items: center; |
| .items-end | align-items: flex-end; |
| .items-baseline | align-items: baseline; |
| .content-start | align-content: flex-start; |
| .content-center | align-content: center; |
| .content-end | align-content: flex-end; |
| .content-betwen | align-content: space-between; |
| .content-around | align-content: space-around; |
| .self-auto | align-self: auto; |
| .self-start | align-self: flex-start; |
| .self-center | align-self: center; |
| .self-end | align-self: flex-end; |
| .self-stretch | align-self: stretch; |
| .justify-start | justify-content: flex-start; |
| .justify-center | justify-content: center; |
| .justify-end | justify-content: flex-end; |
| .flex-initial | flex: initial; |
| .flex-1 | flex: 1; |
| .flex-2 | flex: 2; |
| .flex-auto | flex: auto; |
| .flex-none | flex: none; |
| .flex-grow | flex-grow: 1; |
| .flex-shrink | flex-shrink: 1; |
| .flex-no-grow | flex-grow: 0; |
| .flex-no-shrink | flex-shrink: 0; |

### Sizing

| Class | Properties |
| --- | --- |
| .w-auto | width: auto; |
| .w-full | width: 100%; |
| .w-screen | width: 100vw; |
| .w-1px | width: 1px; |
| .h-auto | height: auto; |
| .h-full | height: 100%; |
| .h-screen | height: 100vh; |
| .h-1px | height: 1px; |
| .min-w-auto | min-width: auto; |
| .min-w-full | min-width: 100%; |
| .min-w-screen | min-width: 100vw; |
| .min-w-1px | min-width: 1px; |
| .min-w-0 | min-width: 0; |
| .min-h-auto | min-height: auto; |
| .min-h-full | min-height: 100%; |
| .min-h-screen | min-height: 100vh; |
| .min-h-1px | min-height: 1px; |
| .min-h-0 | min-height: 0; |
| .max-w-auto | max-width: auto; |
| .max-w-full | max-width: 100%; |
| .max-w-screen | max-width: 100vw; |
| .max-w-1px | max-width: 1px; |
| .max-w-0 | max-width: 0; |
| .max-h-auto | max-height: auto; |
| .max-h-full | max-height: 100%; |
| .max-h-screen | max-height: 100vh; |
| .max-h-1px | max-height: 1px; |
| .max-h-0 | max-height: 0; |

### Borders

| Class | Properties |
| --- | --- |
| .rounded-{$size} | border-radius: $size; |
| .border-{$color} | border-color: auto; |
| .border-{$corner}-{$radius} | border-{$corner}-radius: $radius; |
| .border-{$width} | border-width: $width; |
| .border-{$side}-{$width} | border-{$side}-width: $width; |
| .border-solid | border-style: solid; |
| .border-dashed | border-style: dashed; |
| .border-dotted | border-style: dotted; |
| .border-inset | border-style: inset; |
| .border-outset | border-style: outset; |

* Border Radius Sizes: ('sm', 'md', 'lg', 'xl')
* Border Width Sizes: ('xs', 'sm', 'md', 'lg', 'xl')

```scss
$steller-colors: (
  'my-color-name': #586f7c,
);
```
```html
<!-- border radius (all 4 corners) -->
<div class="rounded-lg"></div>

<!-- border top -->
<div class="border-top-xs border-my-color-name border-solid"></div>

<!-- rounded bottom right corner only -->
<div class="rounded-br-sm"></div>
```

### Effects

| Class | Properties |
| --- | --- |
| .shadow-{$size} | box-shadow: $size; |
| .opacity-100 | opacity: 1; |
| .opacity-75 | opacity: 0.75; |
| .opacity-50 | opacity: 0.5; |
| .opacity-25 | opacity: 0.25; |
| .opacity-0 | opacity: 0; |

* Box Shadow Sizes: ('sm', 'md', 'lg')

```html
<div class="shadow-md"></div>
```

### Gradients

| Class | Properties |
| --- | --- |
| .bg-gradient-{$gradient-name} | background-image: $gradient; |

```scss
$steller-colors: (
  'my-color-name': #586f7c,
);
```
```html
<div class="bg-gradient-my-gradient-name"></div>
```

### Backgrounds

| Class | Properties |
| --- | --- |
| .bg-attachment-fixed | background-attachment: fixed; |
| .bg-attachment-local | background-attachment: local; |
| .bg-attachment-scroll | background-attachment: scroll; |
| .bg-position-bottom | background-position: bottom; |
| .bg-position-center | background-position: center; |
| .bg-position-left | background-position: left; |
| .bg-position-left-bottom | background-position: left-bottom; |
| .bg-position-left-top | background-position: left-top; |
| .bg-position-right | background-position: right; |
| .bg-position-right-bottom | background-position: right-bottom; |
| .bg-position-right-top | background-position: right-top; |
| .bg-position-top | background-position: top; |
| .bg-repeat | background-repeat: repeat; |
| .bg-no-repeat | background-repeat: no-repeat; |
| .bg-repeat-x | background-repeat: repeat-x; |
| .bg-repeat-y | background-repeat: repeat-y; |
| .bg-size-auto | background-size: auto; |
| .bg-size-cover | background-size: cover; |
| .bg-size-contain | background-size: contain; |

### Interactivity

| Class | Properties |
| --- | --- |
| .appearance-none | appearance: none; |
| .cursor-auto | cursor: auto; |
| .cursor-default | cursor: default; |
| .cursor-pointer | cursor: pointer; |
| .cursor-wait | cursor: wait; |
| .cursor-move | cursor: move; |
| .cursor-not-allowed | cursor: not-allowed; |
| .outline-none | outline: none; |
| .pointer-events-none | pointer-events: none; |
| .pointer-events-auto | pointer-events: auto; |
| .resize-none | resize: none; |
| .resizable | resize: both; |
| .resizable-y | resize: vertical; |
| .resizable-x | resize: horizontal; |
| .user-select-text | user-select: text; |
| .user-select-none | user-select: none; |

### Table

| Class | Properties |
| --- | --- |
| .table-auto | table-layout: auto; |
| .table-fixed | table-layout: fixed; |
| .border-collapse | border-collapse: collapse; |
| .border-seperate | border-collapse: separate; |

### SVG

| Class | Properties |
| --- | --- |
| .fill-current | fill: currentColor; |
| .stroke-current | stroke: currentColor; |

## State Variants

### Responsive

For breakpoint specific stylings, add the breakpoint label prefix to the beginning of the class.

```html
<span class="text-success md:text-danger">
  I am naturally the success color,
  but I am the danger color above the medium breakpoint
</span>
```

### Hover

To apply a style on hover, prefix the normal class with `hover:`.

```html
<span class="hover:underline">
  I am undelrined on hover!
</span>
```

### Focus

To apply a style on focus, prefix the normal class with `focus:`.

```html
<span class="focus:underline">
  I am undelrined on focus!
</span>
```

### Active

To apply a style on active, prefix the normal class with `active:`.

```html
<span class="active:underline">
  I am undelrined on active!
</span>
```

## Custom CSS

Within a functional CSS paradigm, you hopefully won't be writing that much custom styling in CSS/SCSS files, but you'll likely need to write some for the occasional complex component or feature. Steller recognizes this and exposes all of your theme config variables as [CSS Custom Properties (CSS Variables)](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties) to help you.

Your config
```scss
$steller-colors: (
  'primary': lightblue,
  'secondary': pink,
);

$steller-custom-font-families: (
  'classy': ('Comic Sans', cursive),
);
```

Your feature
```css
.some-complex-element {
  background: linear-gradient(var(--color-primary), var(--color-secondary));
  font-family: var(--font-family-classy);
  font-size: var(--font-size-2xl);
}
```

If you need to support IE and thus can't use CSS variables, you can just reference the Steller theme variables directly or use one of the helper sass functions Steller provides.

```scss
.foo {
  // finds the color named 'primary' in your $steller-colors theme var
  background-color: color('primary');
  // finds the font family named 'classy' in your $steller-custom-font-families theme var
  font-family: font-family('classy');
}
```

## Extending Steller

Steller is extensible via first or third-party modules. Simply add a sass map to the `$steller-modules` variable in your theme conifg (or anywhere before your steller-css import).
[Example.](https://github.com/tjhillard/steller-vue-transitions/blob/master/__tests__/index.scss)

```scss
$steller-modules: (
  $my-module-name,
);
```

Your module variable should look something along these lines:

```scss
$my-module-name: (
  'wumbo': font-size: 100pt,
  'cant-see-u': (opacity: 0, visibility: hidden),
);
```

```html
<span class="cant-see-u md:wumbo">
  Custom classes! :tada:
</span>
```

Classes via steller modules automatically have all prefixed variants available.

---

#### Contributors

* [TJ Hillard (@tjhillard)](https://github.com/tjhillard)
* [Peter Glennon (@pcrglennon)](https://github.com/pcrglennon)

#### Roadmap

* Transform transition speed classes

#### Steller Family

* [steller-vue-transitions](https://github.com/tjhillard/steller-vue-transitions)

#### What is functional/atomic/utility-first CSS?

* [CSS and Scalability by Adam Morse](http://mrmrs.cc/writing/2016/03/24/scalable-css/)
* [Functional CSS at Scale: Clean & composable UI on a massive app](https://www.youtube.com/watch?v=uHVqbCPnOwU)

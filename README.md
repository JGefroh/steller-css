# steller-css ⛰️
Steller is a functional (aka "atomic" or "utility-first") CSS framework for serving as the foundation of your application's design system. It includes several built-in smart defaults for building responsive, accesible, and usable user interfaces. Unlike other CSS frameworks, Steller has no opinion on the actual end appearance of your application, it is simply a bridge for your design system and your application's styling.

## Features
* Simple, centralized configuration ⚙️
* Grid system built with CSS Grid 📏
* Class variants for responsive & hover states 📱
* Built-in responsive typography best practices ✍️
* Clear, predictable class syntax 🔍
* SASS based (No CSS-in-JS complexity) ✨
* Only 12kb gzipped 🚀

## Installation

```
npm i steller-css
```

```
yarn add steller-css
```

## Usage

1. Create a `theme.scss` or `variables.scss`, or whatever name you prefer
2. Copy pasta the values in the [example config](https://github.com/tjhillard/steller-css/blob/master/src/example-theme.scss)
3. Adjust the theme variables to your design system's needs.
4. In your `index.scss` or equivilent, import your newly created `theme.scss` at the top of your entry point sass file
5. Import steller from node_modules
```scss
// Assuming you are using webpack

@import 'steller-theme'; // Your config file
@import '~steller-css/index'; // Steller
```

## Config

All config variables are technically "optional". Override them as you need.

### Colors

```scss
$steller-colors: (
  'dwight-schrute': #0FF1C3,
  'a-song-of-this-and-fire': #1CE,
);
```

### Typogrpahy

```scss
$font-family-heading: 'Some trendy web font', sans-serif;
$font-family-body: 'Comic Sans', sans-serif;

$steller-custom-font-families: (
  'accent': cursive,
);

$font-size-xs: 10px;
$font-size-sm: 12px;
$font-size-md: 16px; // 👈 <html> default
$font-size-lg: 22px;
$font-size-xl: 28px;
$font-size-2xl: 34px;
$font-size-3xl: 46px;
$font-size-4xl: 58px;

$font-weight-bold: 700;
$font-weight-medium: 500;
$font-weight-regular: 400;
$font-weight-light: 300;
$font-weight-thin: 100;

$leading-sm: 1.25em;
$leading-md: 1.5em;
$leading-lg: 2em;
```

### Breakpoints

```scss
$breakpoint-sm: 380px;
$breakpoint-md: 600px;
$breakpoint-lg: 980px;
```

### Container

```scss
$container-width: 1140px;
```

### Grid

```scss
$grid-columns: 12;

$column-gutter-sm: 16px;
$column-gutter-md: 16px;
$column-gutter-lg: 24px;

$row-gutter-sm: 8px;
$row-gutter-md: 8px;
$row-gutter-lg: 16px;
```

### Spacing

```scss
$spacing-xs: 4px;
$spacing-sm: 8px;
$spacing-md: 16px;
$spacing-lg: 24px;
$spacing-xl: 32px;
$spacing-2xl: 48px;
$spacing-3xl: 64px;
```

### Borders

```scss
$border-radius-sm: 5px;
$border-radius-md: 10px;
$border-radius-lg: 15px;
$border-radius-xl: 20px;

$border-width-xs: 1px;
$border-width-sm: 2px;
$border-width-md: 4px;
$border-width-lg: 6px;
$border-width-xl: 8px;
```

### Motion

```scss
$speed-extra-slow: 500ms;
$speed-slow: 400ms;
$speed-normal: 300ms;
$speed-fast: 200ms;
$speed-extra-fast: 100ms;
```

### Effects

```scss
$box-shadow-sm: 0 7px 15px 0 rgba(0, 0, 0, 0.11), 0 1px 8px 0 rgba(0, 0, 0, 0.06);
$box-shadow-md: 0 10px 20px 0 rgba(0, 0, 0, 0.22), 0 3px 12px 0 rgba(0, 0, 0, 0.07);
$box-shadow-lg: 0 15px 30px 0 rgba(0, 0, 0, 0.33), 0 5px 15px 0 rgba(0, 0, 0, 0.1);
```

## Functional Classes

### Container
| Class | Properties |
| --- | --- |
| .container | margin: 0 auto; max-width: $container-width; position: relative; |

### Grid

Codepen Example: https://codepen.io/tjhillard/pen/WmYEJG

| Class | Properties |
| --- | --- |
| .grid | display: grid; grid-template-columns: repeat($grid-columns, 1fr); |
| .col-{$breakpont}-{$span} | grid-column: span $span; |
| .row-{$breakpont}-{$span} | grid-row: span $span; |
| .col-start-{$breakpont}-{$span} | grid-column: $span / span $i; |

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

### Color

| Class | Properties |
| --- | --- |
| .text-{$color} | color: $color; |
| .bg-{$color} | background-color: $color; |

## Layout

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
| .no-user-select | user-select: none; |

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

## Borders

| Class | Properties |
| --- | --- |
| .border-{$color} | border-color: auto; |
| .border-{$radius} | border-radius: $radius; |
| .border-{$corner-or-side}-{$radius} | border-{$corner-or-side}-radius: $radius; |
| .border-{$width} | border-width: $width; |
| .border-{$corner-or-side}-{$width} | border-{$corner-or-side}-width: $width; |
| .border-solid | border-style: solid; |
| .border-dashed | border-style: dashed; |
| .border-dotted | border-style: dotted; |
| .border-inset | border-style: inset; |
| .border-outset | border-style: outset; |

## Effects

| Class | Properties |
| --- | --- |
| .shadow-{$size} | box-shadow: $size; |

(Box Shadow sizes are defined in your steller config)

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

#### Roadmap

* WIP

#### Example applications using steller-css

* [tjhillard.com | GitHub](https://github.com/tjhillard/tjhillard.com)

#### Steller family

* steller-vue-components (wip)
* steller-vue-transitions (wip)

#### Want to learn more about functional/atomic/utility-frist CSS?

* [CSS and Scalability by Adam Morse](http://mrmrs.cc/writing/2016/03/24/scalable-css/)
* [Functional CSS at Scale: Clean & composable UI on a massive app](https://www.youtube.com/watch?v=uHVqbCPnOwU)

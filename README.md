# sanitize-4d.css [<img src="https://csstools.github.io/sanitize-4d.css/logo.svg" alt="sanitize" width="90" height="90" align="right">][sanitize-4d.css]

[![Greenkeeper badge](https://badges.greenkeeper.io/fourdigit/sanitize-4d.css.svg)](https://greenkeeper.io/)

[sanitize-4d.css] is a CSS library that provides consistent, cross-browser
default styling of HTML elements alongside useful defaults.


## How to get it

**NPM**

```sh
npm install --save @fourdigit/sanitize-4d.css
```

### Usage in npm and webpack

Import [sanitize-4d.css] in CSS:

```css
@import '~@fourdigit/sanitize-4d.css';
```

Alternatively, import [sanitize-4d.css] in JS:

```js
import '@fourdigit/sanitize-4d.css';
```

In `webpack.config.js`, be sure to use the appropriate loaders:

```js
module.exports = {
  module: {
    rules: [
      {
        test: /\.css$/,
        use: [ 'style-loader', 'css-loader' ]
      }
    ]
  }
}
```

## What does it do?

* Normalizes styles for a wide range of elements.
* Corrects bugs and common browser inconsistencies.
* Provides common, useful defaults.
* Explains what code does using detailed comments.

## Features

##### Box sizing defaults to border-box

```css
*, ::before, ::after {
  box-sizing: border-box;
}
```

##### Backgrounds do not repeat by default

```css
*, ::before, ::after {
  background-repeat: no-repeat;
}
```

##### Pseudo-elements inherit text decoration and vertical alignment

```css
::before,
::after {
  text-decoration: inherit;
  vertical-align: inherit;
}
```

##### Cursors only change to hint non-obvious interfaces

```css
html {
  cursor: default;
}
```

##### The default font is the system ui font

```css
html {
  font-family:
    system-ui,
    /* macOS 10.11-10.12 */ -apple-system,
    /* Windows 6+ */ Segoe UI,
    /* Android 4+ */ Roboto,
    /* Ubuntu 10.10+ */ Ubuntu,
    /* Gnome 3+ */ Cantarell,
    /* KDE Plasma 5+ */ Noto Sans,
    /* fallback */ sans-serif,
    /* macOS emoji */ "Apple Color Emoji",
    /* Windows emoji */ "Segoe UI Emoji",
    /* Windows emoji */ "Segoe UI Symbol",
    /* Linux emoji */ "Noto Color Emoji";
}
```

#### Line height correction in all browsers

```css
html {
  line-height: 1.15;
}
```

##### Tabs appear the same on the web as in a typical editor

```css
html {
  -moz-tab-size: 4;
  tab-size: 4;
}
```

##### Words break to prevent overflow

```css
html {
  word-break: break-word;
}
```

##### Prevent adjustments of font size after orientation changes in IE on Windows Phone and in iOS

```css
html {
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
}
```

##### Font rendering settings;  1x => subpixel、2x or higher => grayscale http://creator.dwango.co.jp/14128.html

```css
html {
  -webkit-font-smoothing: subpixel-antialiased;
  -moz-osx-font-smoothing: unset;
}

@media only screen and
  (-webkit-min-device-pixel-ratio: 2),
  (min-resolution: 2dppx) {
  html {
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  }
}
```

##### Documents do not use a margin for outer padding

```css
body {
  margin: 0;
}
```

##### `h1` font-size and margin correction

```css
h1 {
  font-size: 2em;
  margin: 0.67em 0;
}
```

##### `hr` sizing correction in Firefox. Show the overflow in Edge and IE

```css
hr {
  height: 0;
  overflow: visible;
}
```

##### `main` display correction in IE

```css
main {
  display: block;
}
```

##### Navigation lists do not include a marker style

```css
nav ol, nav ul {
  list-style: none;
}
```

##### Active link's gray background removal in IE 10

```css
a {
  background-color: transparent;
}
```

##### Abbreviations's title text decoration correction in Edge, IE, Opera, and Safari

```css
abbr[title] {
  text-decoration: underline;
  text-decoration: underline dotted;
}
```

##### `b` and `strong` font weight correction in Chrome, Edge, and Safari

```css
b,
strong {
  font-weight: bolder;
}
```

##### Pre-formatted and code-formatted text uses the monospace system ui font

```css
code, kbd, pre, samp {
  font-family:
    /* macOS 10.10+ */ Menlo,
    /* Windows 6+ */ Consolas,
    /* Android 4+ */ Roboto Mono,
    /* Ubuntu 10.10+ */ Ubuntu Monospace,
    /* KDE Plasma 5+ */ Noto Mono,
    /* KDE Plasma 4+ */ Oxygen Mono,
    /* Linux/OpenOffice fallback */ Liberation Mono,
    /* fallback */ monospace;
}
```

##### Pre-formatted and code-formatted text font-size

```css
code, kbd, pre, samp {
  font-size: 1em;
}
```

##### `small` font-size correction

```css
small {
  font-size: 80%;
}
```
##### Text selections do not include text shadows

```css
::-moz-selection {
  background-color: #b3d4fc;
  color: #000;
  text-shadow: none;
}

::selection {
  background-color: #b3d4fc;
  color: #000;
  text-shadow: none;
}
```

##### Media elements align to the text center of other content

```css
audio, canvas, iframe, img, svg, video {
  vertical-align: middle;
}
```

##### `video` and `audio` display correction in IE 9-

```css
audio,
video {
  display: inline-block;
}
```

##### `audio` display correction in iOS 4-7

```css
audio:not([controls]) {
  display: none;
  height: 0;
}
```

##### Image inside link should has no border in IE 10-

```css
img {
  border-style: none;
}
```

##### SVGs fallback to the current text color

```css
svg:not([fill]) {
  fill: currentColor;
}
```

##### SVGs hide overflow in IE

```css
svg:not(:root) {
  overflow: hidden;
}
```

##### Tables do not include additional border spacing

```css
table {
  border-collapse: collapse;
}
```

##### Form controls are easily style-able

```css
button, input, select, textarea {
  font-family: inherit;
  font-size: inherit;
  line-height: inherit;
}
```

##### `button`, `input`, `select` should have no margin in Safari

```css
button,
input,
select {
  margin: 0;
}
```

##### `button` show the overflow in IE

```css
button {
  overflow: visible;
}
```

##### `button` should not inheri text transform in Edge, Firefox, and IE

```css
button {
  text-transform: none;
}
```

##### Clickable types should be stylable in iOS and Safari

```css
button,
[type="button"],
[type="reset"],
[type="submit"] {
  -webkit-appearance: button;
}
```

##### `fieldset` padding correction in Firefox

```css
fieldset {
  padding: 0.35em 0.75em 0.625em;
}
```

##### `input` shows overflow in Edge and IE

```css
input {
  overflow: visible;
}
```

##### `legend` text wrapping correction in Edge and IE

```css
legend {
  display: table;
  max-width: 100%;
  white-space: normal;
}
```

##### `legend` should inherit color from `fieldset` elements in IE

```css
legend {
  color: inherit;
}
```

##### `progress`: Add the correct display in Edge and IE

```css
progress {
  display: inline-block;
}
```

##### `progress`: Add the correct vertical alignment in Chrome, Firefox, and Opera

```css
progress {
  vertical-align: baseline;
}
```

##### `select`: Remove the inheritance of text transform in Firefox

```css
select {
  text-transform: none;
}
```

##### Textareas only resize vertically by default

```css
textarea {
  resize: vertical;
}
```

##### Textareas has no margin in Firefox and  Safari

```css
textarea {
  margin: 0;
}
```

##### Textareas's default vertical scrollbar removal in IE

```css
textarea {
  overflow: auto;
}
```

##### Checkboxes and radios padding removal on IE 10-

```css
[type="checkbox"],
[type="radio"] {
  padding: 0;
}
```

##### Search input odd appearance correction in Chrome and Safari

```css
[type="search"] {
  -webkit-appearance: textfield;
}
```

##### Search input outline style correction in Safari

```css
[type="search"] {
  outline-offset: -2px;
}
```

##### increment and decrement buttons cursor style correction in Safari

```css
::-webkit-inner-spin-button,
::-webkit-outer-spin-button {
  height: auto;
}
```

##### Placeholders text style correction in Chrome, Edge and Safari

```css
::-webkit-input-placeholder {
  color: inherit;
  opacity: 0.54;
}
```

##### Search input inner padding removal in Chrome and Safari on macOS

```css
::-webkit-search-decoration {
  -webkit-appearance: none;
}
```

##### File upload button: Correct the inability to style clickable types in iOS and Safari

```css
::-webkit-file-upload-button {
  -webkit-appearance: button;
}
```

##### File upload button: Change font properties to `inherit` in Safari

```css
::-webkit-file-upload-button {
  font: inherit;
}
```

##### Focus outline: remove the inner border and padding in Firefox

```css
::-moz-focus-inner {
  border-style: none;
  padding: 0;
}
```

##### Focus outline: restore the focus styles unset by the previous rule in Firefox

```css
:-moz-focusring {
  outline: 1px dotted ButtonText;
}
```

##### Details: display correction in Edge and IE

```css
details {
  display: block;
}
```

##### Dialogs: style correction in Edge, IE and Safari

```css
dialog {
  background-color: white;
  border: solid;
  color: black;
  display: block;
  height: -moz-fit-content;
  height: -webkit-fit-content;
  height: fit-content;
  left: 0;
  margin: auto;
  padding: 1em;
  position: absolute;
  right: 0;
  width: -moz-fit-content;
  width: -webkit-fit-content;
  width: fit-content;
}

dialog:not([open]) {
  display: none;
}
```

##### Summary: correct display in all browsers

```css
summary {
  display: list-item;
}
```

##### Canvas: display correction in IE 9-

```css
canvas {
  display: inline-block;
}
```

##### Temmplate: display correction in IE

```css
template {
  display: none;
}
```

##### Single taps are dispatched immediately on clickable elements

```css
a, area, button, input, label, select, summary, textarea, [tabindex] {
  -ms-touch-action: manipulation;
  touch-action: manipulation;
}
```

##### Correct display of hidden element in IE 10-

```css
[hidden] {
  display: none;
}
```

##### ARIA roles include visual cursor hints

```css
[aria-busy="true"] {
  cursor: progress;
}

[aria-controls] {
  cursor: pointer;
}

[aria-disabled="true"], [disabled] {
   cursor: not-allowed;
}
```

##### Visually hidden content remains accessible

```css
[aria-hidden="false"][hidden]:not(:focus) {
  clip: rect(0, 0, 0, 0);
  display: inherit;
  position: absolute;
}
```

## Differences

[normalize.css] and [sanitize-4d.css] correct browser bugs while carefully testing
and documenting changes. normalize.css styles adhere to css specifications.
sanitize-4d.css styles adhere to common developer expectations and preferences.
[reset.css] unstyles all elements. Both sanitize-4d.css and normalize.css are
maintained in sync.

## Browser support

* Chrome (last 3)
* Edge (last 3)
* Firefox (last 3)
* Firefox ESR
* Opera (last 3)
* Safari (last 3)
* iOS Safari (last 2)
* Internet Explorer 9+

## Contributing

Please read the [contribution guidelines](CONTRIBUTING.md) in order to make the
contribution process easy and effective for everyone involved.

## Acknowledgements

sanitize.css is a project by [Jonathan Neal](https://github.com/jonathantneal),
built upon normalize.css, a project by
[Jonathan Neal](https://github.com/jonathantneal),
co-created with [Nicolas Gallagher](https://github.com/necolas).

[normalize.css]: https://github.com/csstools/normalize.css
[reset.css]: http://meyerweb.com/eric/tools/css/reset/
[sanitize.css]: https://github.com/csstools/sanitize.css
[sanitize-4d.css]: https://github.com/csstools/sanitize-4d.css

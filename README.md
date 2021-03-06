# 🎨 CSS Theme Change 
A very very small script to handle CSS theming  

[![][build]][build-url] [![][install-size]][install-size-url] [![][js]][js-url]  
[![][npm]][npm-url] [![][dl]][npm-url] [![][commit]][gh-url]  

> Change CSS theme with toggle, buttons or select using CSS Variables ([CSS custom properties](https://developer.mozilla.org/en-US/docs/Web/CSS/--*)) and [localStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage).  
It saves the chosen theme in brower localStorage and loads it again when page loads.  
You only need to define your theme in CSS  
  
# Demo  
- See example code on [codepen](https://codepen.io/saadeghi/pen/OJypbNM)
- See Sample site on [Netlify](https://css-theme-changer.netlify.app/)

[![image](https://user-images.githubusercontent.com/7342023/80218042-e3c67e00-8655-11ea-94e8-925d0dcbfd57.gif)](#)


# 👨‍💻 Use  

- You can use 3 methods:
  1. [Change theme with buttons](#1%EF%B8%8F⃣-change-theme-with-buttons)
  2. or [toggle between 2 themes](#2%EF%B8%8F⃣--toggle-between-2-themes)
  3. or [using a select element to choose theme](#3%EF%B8%8F⃣-using-a-select-to-choose-theme)
- Then you need to [define your theme in CSS](#set-up-your-css)

---
## 1️⃣ Change theme with buttons
[![btn](https://user-images.githubusercontent.com/7342023/101527827-c0adcc00-39a3-11eb-9e41-24bfa91ea96c.gif)](#)


Using `data-set-theme`
Clicking on these buttons, sets the chosen theme and also adds the `ACTIVECLASS` to the chosen button

### HTML
```
<button data-act-class="ACTIVECLASS" data-set-theme=""></button>
<button data-act-class="ACTIVECLASS" data-set-theme="dark"></button>
<button data-act-class="ACTIVECLASS" data-set-theme="pink"></button>
```
### JS 
Use CDN [![][btn-js]][btn-js-url]  
```
<script src="https://unpkg.com/theme-change@latest/dist/btn.js"></script>
```
Or use NPM:  
Install: `npm i theme-change --save` and use it in your js file:  
```
import {themeBtn} from "theme-change"
themeBtn()
```

## 2️⃣  Toggle between 2 themes 
[![toggle](https://user-images.githubusercontent.com/7342023/101527821-bf7c9f00-39a3-11eb-822b-7751265a18a5.gif)](#)

Using `data-toggle-theme`
Clicking on this element, toggles between the 2 values and applies the ACTIVECLASS when dark theme is active

### HTML
```
<button data-act-class="ACTIVECLASS" data-toggle-theme="dark,light"></button>
```
### JS 
Use CDN [![][toggle-js]][toggle-js-url]  
```
<script src="https://unpkg.com/theme-change@latest/dist/toggle.js"></script>
```
Or use NPM:  
Install: `npm i theme-change --save` and use it in your js file:  
```
import {themeToggle} from "theme-change"
themeToggle()
```

## 3️⃣ Using a `<select>` to choose theme 
[![select](https://user-images.githubusercontent.com/7342023/101527790-b4297380-39a3-11eb-9173-bc909549d160.gif)](#)

Using `data-choose-theme`
set theme when `<select>` changes
### HTML
```
<select data-choose-theme>
  <option value="">Default</option>
  <option value="dark">Dark</option>
  <option value="pink">Pink</option>
</select>
```
### JS 
Use CDN [![][select-js]][select-js-url]  
```
<script src="https://unpkg.com/theme-change@latest/dist/select.js"></script>
```
Or use NPM:  
Install: `npm i theme-change --save` and use it in your js file:  
```
import {themeSelect} from "theme-change"
themeSelect()
```

---

# Set up your CSS
Set your themeable style as custom properties in CSS like this:  
```
:root {
  --color-default: #fff;
  /* or any other variables */
}
[data-theme='dark'] {
  --color-default: #252b30;
}
[data-theme='pink'] {
  --color-default: #ffabc8;
}
```
then use your variables on any element
```
body {
  background-color: var(--color-default);
}
```
##### Set default theme for dark mode users
You can also define a default theme when user is using a dark theme on their OS
```
@media (prefers-color-scheme: dark){
  --color-default: #252b30;
}
```
##### Fixing PurgeCSS issue
⚠️ If you're using [Purge CSS](https://purgecss.com/), you might need to [safe list](https://purgecss.com/safelisting.html#in-the-css-directly) your CSS using the comments below because your secondary themes will be purged
```
/*! purgecss start ignore */

[data-theme='dark'] {
  --color-default: #252b30;
}

/*! purgecss end ignore */
```

---
[install-size]: https://badgen.net/packagephobia/publish/theme-change?label=package%20install%20size&icon=npm&color=purple
[js]: https://badgen.net/badgesize/normal/https/unpkg.com/theme-change/dist/index.js?label=file%20size&color=purple
[btn-js]: https://badgen.net/badgesize/normal/https/unpkg.com/theme-change/dist/btn.js?label=size&color=purple&scale=0.8
[toggle-js]: https://badgen.net/badgesize/normal/https/unpkg.com/theme-change/dist/toggle.js?label=size&color=purple&scale=0.8
[select-js]: https://badgen.net/badgesize/normal/https/unpkg.com/theme-change/dist/select.js?label=size&color=purple&scale=0.8
[npm]: https://badgen.net/npm/v/theme-change?label=version&color=purple
[dl]: https://badgen.net/npm/dt/theme-change?icon=npm&color=purple
[commit]: https://badgen.net/github/last-commit/saadeghi/theme-change?icon=github&color=purple
[build]: https://badgen.net/github/checks/saadeghi/theme-change?label=build

[build-url]: https://github.com/saadeghi/theme-change/actions
[install-size-url]: https://packagephobia.com/result?p=theme-change
[js-url]: https://unpkg.com/theme-change@latest/dist/index.js
[btn-js-url]: https://unpkg.com/theme-change@latest/dist/btn.js
[toggle-js-url]: https://unpkg.com/theme-change@latest/dist/toggle.js
[select-js-url]: https://unpkg.com/theme-change@latest/dist/select.js
[npm-url]: https://www.npmjs.com/package/theme-change
[gh-url]: https://github.com/saadeghi/theme-change

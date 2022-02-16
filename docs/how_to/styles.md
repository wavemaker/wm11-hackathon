---
title:  How to style app using app.css and page styles?
layout: default
parent: How To
nav_exclude: true
---

# {{ page.title }}


In reactnative app, styles are expressed as javascript object. Refer [https://reactnative.dev/docs/style](https://reactnative.dev/docs/style). These styles are similar to css styles but with different names. When compared to css properties, reactnative style properties are very limited. Check the list of [supported properties here](https://reactnative.dev/docs/image-style-props).

In WaveMaker, partial support is added to mention styles in CSS format. In studio, As we type in page styles, auto suggestions for component classes will be populated in the style editor.
![Styles Auto Suggestion](../../assets/styles_auto_suggestion.png)

For suppose, in sample application drag and drop a button. If you want customize the style of this particular button, then give a class name to the button (lets say custom-btn) in the properties panel. Here, you want to change the background-color of the button and color of the text inside button.
 - For changing background color, just using .custom-btn.app-button class will work.
 - For changing text color, just using .custom-btn.app-button-text class will work.
 ![Button Styles](../../assets/button-styles.png)

Follow the below way of defining styles. 
```
.app-button - will target all buttons
.custom-btn.app-button - will target only buttons that have custom-btn class.
```

**Limitations** 
1. Users must define styles targeting auto suggested class names only. 
2. Expect class names, no other css selector definitions are supported. Also do not write any styles specific to dom selector.
3. Cascading of styles from parent to children is also not supported.
For example, a container has a class “.custom-container”. If you need to change the css of the button placed inside it, then this can be expressed as below in normal css.
```
.custom-container > .app-button {
    background-color: ‘red’;
}
```
whereas in reactnative, you must target the button directly. Styles of the container will not get passed to the button. In this case, a class has to be mentioned on that button and styles have to specified to that class.
```
.custom-container.app-container {
    background-color: red;
}
.custom-btn.app-button {
    background-color: red;
}
```

All these CSS styles are converted to js object during code generation.

## Order of styles computed (Bottom to top)
1. Inline styles
2. page.css
3. app.css
4. Theme
5. Runtime default styles


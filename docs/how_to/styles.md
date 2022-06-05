---
title:  How to style app using app.css and page styles?
layout: default
parent: How To
nav_exclude: true
---

# {{ page.title }}


In reactnative app, styles are expressed as javascript object. Refer [https://reactnative.dev/docs/style](https://reactnative.dev/docs/style). These styles are similar to css styles but with different names. When compared to css properties, reactnative style properties are very limited. Check the list of [View Style](../features/widgets/view.style.html), [Text Style](../features/widgets/text.style.html) and [Image Style](../features/widgets/image.style.html).

In WaveMaker, partial support is added to mention styles in CSS format. Let us take a button as an example. In button, there are 3 stylable units. They are 1) container, 2) text and 3) icon. For each of these stylable units, unique classnames is assigned. They are 1) app-button, 2) app-button-text and 3) app-button-icon. Using these classnames, styles can be mentioned in theme, app.css and page styles. In this way, every WaveMaker widget has several stylable units. In [Widgets page](../features/widgets.html), there is a link to style document across each widget. In studio, As we type in page styles, auto suggestions for classnames will be populated in the style editor.
![Styles Auto Suggestion](../../assets/styles_auto_suggestion.png)


For suppose, in sample application drag and drop a button. If you want customize the style of this particular button, then give a class name to the button (lets say custom-btn) in the properties panel. Here, you want to change the background-color of the button and color of the text inside button.
 - For changing background color, just using .custom-btn.app-button class will work.
 - For changing text color, just using .custom-btn.app-button-text class will work.
 ![Button Styles](../../assets/button-styles.png)

Following is the way to specify styles. 
```
.app-button - will target all buttons
.custom-btn.app-button - will target only buttons that have custom-btn class.
```

Some widgets use WaveMaker widgets internally. For Example, button use icon internally. Following is the way to change the color of the icon.
```
.custom-btn.app-button-icon.app-icon-shape {
    color : red;
}
```
**Limitations** 
1. Users must define styles targeting auto suggested class names only (or stylable units). 
2. Expect class names, no other css selector definitions are supported. Also do not write any styles specific to dom selector.
3. Using parent class name selector is not supported.
For example, a container has a class “.custom-container”. If you need to change the css of the button placed inside it, then this can be expressed as below in normal css.
```
.custom-container > .app-button {
    background-color: ‘red’;
}
```
whereas in reactnative, you must target the button directly. In this case, a class has to be mentioned on that button and styles have to specified to that class.
```
.custom-container.app-container {
    background-color: red;
}
.custom-btn.app-button {
    background-color: red;
}
```

4.  There is no style property inheritance support in React Native. Due to this, Views shown in web preview may differ when the app is opened in mobile. In the above example, styles of the container donot not get passed to the button.   

All these CSS styles are converted to js object during code generation.

## Order of styles computed (Bottom to top)
1. Inline styles
2. page.css
3. app.css
4. Theme
5. Runtime default styles


# The CSS Position Property

In this note, we'll explain how you can use position in CSS to edit the layout of your webpage. We'll explore different position types and review how you can position elements like text and images to create an engaging website.

## What is the CSS position property?

The CSS position property is used to specify where an element is displayed on the page. When paired with the the top, right, bottom, and left CSS properties, the position property determines the final location of the element.

The position property can take one of several values: `static`, `relative`, `fixed`, `absolute`, and `sticky`. Let’s break down each value in detail with examples to see how each value affects a page element.

### CSS Position Values

1. Static
2. Relative
3. Fixed
4. Absolute
5. Sticky

### **Static**

Static is the default position for HTML elements. Elements with `position: static `are positioned based on the normal flow of the page, as you would expect them to be without any CSS styling. They are not affected by the top, right, bottom, or left properties. Z-index also does not apply to static elements.

In the example below, only div 2 is assigned `position: static`. However, you’ll see that its placement in the document is the same as if it did not have this property. You can delete the `position: static` from the CSS and the display will not change.

```html
<div id="div-1">1</div>
<div id="div-2">2</div>
<div id="div-3">3</div>
```

```css
#div-1 {
  background-color: #ff5c35;
}

#div-2 {
  position: static;
  background-color: #0068b1;
}

#div-3 {
  background-color: #4fb06d;
}

div {
  width: 75px;
  height: 75px;
  margin: 10px;
  border-radius: 10px;
  text-align: center;
  line-height: 75px;
  color: white;
  font-size: 24px;
}
```

<div align="center">

![](./images/css%20position/static.PNG)

</div>
Nothing too exciting here. Next, let’s see how we can change an element’s position from the default.

### **Relative**

When assigned `position: relative`, an element follows the render flow of the page, but will be shifted relative to its initial position.

To determine the amount of offset, you set values for the `top`, `right`, `bottom`, and/or `left` properties. Surrounding elements won’t be affected, but there will be space where the repositioned element would have been (in static positioning).

In this example, I’ve offset div 2 by 30 pixels down (with the `top` property) and 30 pixels to the right (using the `left` property). The repositioned div does not affect the position of surrounding elements.

```html
<div id="div-1">1</div>
<div id="div-2">2</div>
<div id="div-3">3</div>
```

```css
#div-1 {
  background-color: #ff5c35;
}

#div-2 {
  position: relative;
  top: 30px;
  left: 30px;
  background-color: #0068b1;
}

#div-3 {
  background-color: #4fb06d;
}

div {
  width: 75px;
  height: 75px;
  margin: 10px;
  border-radius: 10px;
  text-align: center;
  line-height: 75px;
  color: white;
  font-size: 24px;
}
```

<div align="center">

![](./images/css%20position/relative.PNG)

</div>

### **Fixed**

Elements with `position: fixed` do not adhere to the normal render flow of the document. Instead, fixed elements are positioned relative to the viewport — in other words, the part of the document that is currently visible in the browser.

Fixed elements do not move when the user scrolls, and, unlike `relative`, they do not leave a blank space where the element would have been positioned. You can use the `top`, `right`, `bottom`, and `left` properties to set the fixed element's final position.

Here, div 2 is offset by 30 pixels top and 30 pixels left, like in the last example. However, this time it is positioned relative to the viewport. Notice that there is no space where the element would have been on the page.

```html
<div id="div-1">1</div>
<div id="div-2">2</div>
<div id="div-3">3</div>
```

```css
body {
  height: 400vh;
}
#div-1 {
  background-color: #ff5c35;
}

#div-2 {
  position: fixed;
  top: 30px;
  left: 30px;
  background-color: #0068b1;
}

#div-3 {
  background-color: #4fb06d;
}

div {
  width: 75px;
  height: 75px;
  margin: 10px;
  border-radius: 10px;
  text-align: center;
  line-height: 75px;
  color: white;
  font-size: 24px;
}
/* scroll the page and the div with position fixed remains */
```

<div align="center">

![fixed](./images/css%20position/fixed.PNG)

</div>

### **Absolute**

With `position: absolute`, an element ignores the normal document flow. However, instead of being positioned relative to the viewport (like with `position: fixed`), it’s positioned relative to the nearest positioned ancestor (a positioned ancestor is any element with a `position` value besides `static`, the default).

Here, div 2 is placed inside a container div (in gray) and positioned relative to the container, since the container is the nearest ancestor element of div 2.

```html
<div id="div-1">1</div>
<div id="container">
  <div id="div-2">2</div>
</div>
<div id="div-3">3</div>
```

```css
body {
  height: 400vh;
}
#div-1 {
  background-color: #ff5c35;
}

#div-2 {
  position: absolute;
  top: 20px;
  left: 30px;
  background-color: #0068b1;
}

#div-3 {
  background-color: #4fb06d;
}

div {
  width: 75px;
  height: 75px;
  margin: 10px;
  border-radius: 10px;
  text-align: center;
  line-height: 75px;
  color: white;
  font-size: 24px;
}

#container {
  background-color: #b6c7d6;
  width: 200px;
  height: 150px;
  position: relative;
}
```

<div align="center">

![](./images/css%20position/absolute.PNG)

</div>

If there’s no positioned ancestor, the element is positioned relative to the containing block and moves with scrolling.

### **Sticky**

Elements with `position: sticky` are positioned depending on the user’s scroll. Depending on how far the user has scrolled down the page, a sticky element behaves like a relative element until the viewport meets a specified position. Then it becomes fixed in a spot and appears to “stick” to the page as the user scrolls.

In this example, scroll down and watch as div 2 goes from behaving like a relative element to a fixed element when it reaches the position` top: 0` and “sticks” to the top of the viewport.

```html
<div id="div-1">1</div>
<div id="div-2">2</div>
<div id="div-3">3</div>
<div class="generic"></div>
<div class="generic"></div>
<div class="generic"></div>
<div class="generic"></div>
<div class="generic"></div>
<div class="generic"></div>
<div class="generic"></div>
```

```css
body {
  height: 400vh;
}
#div-1 {
  background-color: #ff5c35;
}

#div-2 {
  position: sticky;
  top: 0px;
  background-color: #0068b1;
}

#div-3 {
  background-color: #4fb06d;
}

div {
  width: 75px;
  height: 75px;
  margin: 10px;
  border-radius: 10px;
  text-align: center;
  line-height: 75px;
  color: white;
  font-size: 24px;
}

.generic {
  background-color: lightgray;
}
```

When you scroll the page the div with position sticky become fixed whwn it gets to 0 from the top of the page

## **CSS Position: Relative vs. Absolute**

When an element's computed position value is defined as fixed or absolute, it assumes the absolute CSS position. When the computed position value is relative, it assumes the relative CSS position. In both cases, the top, right, bottom, and left properties specify the offsets from the element's position.

While relative-positioned elements remain in the flow of the document, absolute-positioned elements are taken out of the way of the other elements on the page. All other elements are positioned out as if the absolute-positioned element were not there.

The example below illustrated the difference between static, relative, and absolute positioning. In each gray box, the second paragraph element (highlighted in blue) is positioned differently.

```html
<div class="container">
  <h2>static</h2>
  <p>I'm the first paragraph;</p>
  <p id="static-p">I'm the second paragraph;</p>
  <p>I'm the third paragraph;</p>
</div>

<div class="container">
  <h2>relative</h2>
  <p>I'm the first paragraph;</p>
  <p id="relative-p">I'm the second paragraph;</p>
  <p>I'm the third paragraph;</p>
</div>

<div class="container">
  <h2>absolute</h2>
  <p>I'm the first paragraph;</p>
  <p id="absolute-p">I'm the second paragraph;</p>
  <p>I'm the third paragraph;</p>
</div>
```

```css
.container {
  background-color: lightgray;
  position: relative;
  width: 300px;
  margin: 10px;
  padding: 10px;
}

p,
h2 {
  margin: 5px;
}

#relative-p {
  position: relative;
  top: 40px;
  left: 40px;
}

#absolute-p {
  position: absolute;
  top: 40px;
  left: 40px;
}

#static-p,
#relative-p,
#absolute-p {
  background-color: lightblue;
}
```

<div align="center">

![](./images/css%20position/explain.PNG)

</div>

In the first box, the paragraph is static and appears as expected. In the second box, it is positioned relative to where it would have been in static positioning, shifted 40 pixels down and to the right. In the third box, the paragraph is positioned absolutely — in other words, it is placed relative to its parent element (the gray box container) and the other paragraph elements behave as if it weren’t in the document at all.

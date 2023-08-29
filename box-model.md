# CSS Box Model and Box Sizing

# Introduction

As a web developer, understanding the **CSS box model** is fundamental to crafting a polished user experience. The box model comprises the content, padding, border and margin of an element, and it determines how elements are rendered on the page. Mastering box model unlocks new possibilities for layout and design. We will explore the difference between block and inline elements and how they interact with the box model. Block elements break the normal flow of a page, stacking on top of each other, while inline elements flow with surrounding content. Knowing when to use each element type gives you control over spacing, positioning, and the overall flow of your web pages.

## What is the CSS Box Model?

The **CSS box model** refers to the rectangular boxes that are generated for elements in CSS. Each box has a content area (where the content is displayed) as well as optional border, and margin areas.
The `content area` is the innermost part of the box that contains the actual content. `Padding` is the space around the content. When you set padding, it will push the border and margin outward.
The border area is the area around the padding (if any) and content. Borders sit on top of the padding and content area and separate the margin area from the padding area.
The `margin area` is the outermost layer that surrounds the border. It separates the element from surrounding elements. Margins are transparent, so they allow you to see the background color and background images of the element behind them.
The box model allows us to add spacing and borders around elements in web pages. A basic understanding of the box model is essential for any web developer to style pages effectively.
By default, the width and height you assign to an element only apply to the content area. If you add padding, borders, and margins, it will increase the total size of the box. This is known as box sizing. There are two main box sizing models:

1. **Content-box**: The width and height only apply to the content area. Padding, border, and margin are added outside the content area.
2. **Border-box**: The width and height apply to the content, padding, and border. Margin is added outside. This is the box model used by most browsers today.

To change the box sizing model, use the box sizing property. For example:

```css
.element {
  box-sizing: border-box;
}
```

This will set .element to use the border-box model.

### example

```css
/* Using the content-box (default) box sizing */
.element {
  width: 300px;
  padding: 20px;
  border: 2px solid black;
  margin: 10px;
}
/* the total width here will be 344px */

/* Using the border-box box sizing */
.element {
  width: 300px;
  padding: 20px;
  border: 2px solid black;
  margin: 10px;
  box-sizing: border-box;
}
/* the total width be 300px */
```

##

## Block Level Boxes vs Inline Boxes

`Block elements` occupy the full width of their parent element, stacking on top of each other. Inline elements only take up the space necessary for their content, sitting on the same line. Understanding how these box models work is key to mastering CSS layouts.
Block level boxes have some important characteristics:

1. They force line breaks before and after the element.
2. They occupy the full width of their parent element.
3. Margins and padding apply to the element but do not collapse with margins and padding of inline boxes.
4. The width and height properties are respected.

Some common block level elements are:

`<p>,<div>, <li>, <nav>, <ul>, <ol>, <nav>, <h1> - <h6>, <article>, <footer>, <section>`

`Inline boxes`, on the other hand have different behaviors:

1. They do not force line breaks.
2. They only take up the space necessary for their content.
3. Margins and padding apply but collapse with adjacent inline boxes.
4. The width and height properties are ignored.

Some common inline elements are:

`<a>, <i>, <span>, <button>, <input>, <textarea>, <select>,<time>, <img>`

Understanding block vs inline box models is essential for any web developer. Mastering their differences will give you full control over how elements are laid out on the page.

## Using Display: Block

`display: block` is a powerful tool in CSS for controlling layout, When an element is set to `display: block`, it takes up the full width of its parent container. Each block element starts on a new line, and will stack vertically with other block elements.

## Using Margin and Padding

You can add spacing around block elements using the margin and padding properties. The margin adds spacing outside the element while the padding adds spacing inside. For example:

```css
.block {
  display: block;
  width: 200px;
  margin: 20px;
  padding: 10px;
}
```

This will give the .block element 20px of margin on all sides, and 10px of padding on all side, creating a total of 40px of space between .block elements.

## Controlling Width

`Block elements` will expand to fill the width of their parent container by default. You can give a block element a fixed width using the width property. For example:

```css
.block {
  display: block;
  width: 600px;
}
```

This will make .block 600px wide. If you don’t give a block element a width, it will expand to fill its parent container.

## Using Display: Inline

When working with CSS, understanding how to properly use the display property is essential. The display property specifies the type of box used for an element. It has many possible values, but two of the most common are block and inline.
Block level elements occupy the full width of their parent element. They always start on a new line and stack on top of each other.
Inline elements only occupy the space bounded by the tags defining the element. They do no start on a new line and only take up as much width as necessary.
To change an element to a block or inline, you use the display property:

```css
.div {
  display: block;
}
.span {
  display: inline;
}
```

Setting an element to display: inline will make it act like an inline element, while display: block will make it act like a block element.
Some elements, like `<a>`, are inline by default but are commonly used as block elements. To do this, you just set display: block;as shown below:

```css
a {
  display: block;
}
```

Now the `<a>` element will occupy the full width of its parent and start on its own line.
Using the display property strategically in your CSS allows you to manipulate the default behaviors of elements and build complex layouts. Understanding block vs inline is a foundational concept to mastering CSS.

## Using Display: Inline-Block

display: inline-blockallows block elements to sit next to each other, like inline elements do, while still retaining all the features of block elements. This is useful when you want to have block elements side by side.

Usage
To use inline-block, simply set the display property to inline-block:

```css
.element {
  display: inline-block;
}
```

This will allow the element to behave like an inline element (sitting next to other elements), while still retaining features of a block element (setting width, height, margin, padding, etc).

## Components of the Box Model

1. **Content**: This represents the actual content of an HTML element, such as text, images, or videos. The content area's size is determined by properties like `width` and `height`.

2. **Padding**: Padding is the space between the content and the element's border. It provides a buffer between the content and the border, enhancing the element's appearance and legibility. Padding can be adjusted individually for each side using properties like `padding-top`, `padding-right`, `padding-bottom`, and `padding-left`.

3. **Border**: The border encloses the padding and content and acts as a visual boundary for the element. You can control the border's thickness, color, and style using properties like `border-width`, `border-color`, and `border-style`.

4. **Margin**: Margins are the empty space surrounding an element, creating separation between it and other neighboring elements. Margins can be adjusted with properties like `margin-top`, `margin-right`, `margin-bottom`, and `margin-left`.

<div align="center">

![css box model](https://res.cloudinary.com/practicaldev/image/fetch/s--i8vstu5a--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/eko7ltyx9ca61rwt5oa9.png)

</div>
In the illustration above, the light blue colored section is the Content section. For the above case, it had the dimension indicated above
To understand how the box model works, think of a gift box. The actual present inside is the content. The tissue paper surrounding it is the padding. The decorative wrapping paper is the border. And the empty space between the gift and other gifts is the margin.
The box model allows us to add spacing and borders around elements in a consistent way. Its important to note that the total width of an element is the width of the content plus the padding, border, and margin. This is known as box sizing and can cause issues if you are not aware of it.

## The Box Model and Box Sizing

By default, browsers add the padding, border, and margin to the width you specify. For example, if you set an element to have:

```css
.element{
  width: 200px
  padding: 20px
  border: 5px
  margin: 15px
}
```

The actual rendered width of the element will be 260px (200px + 20px padding + 10px border + 15px margin on each side).
To fix this issue, you can set the box-sizing property to border-box. This will make the width you set equal to the content width plus the padding and border, and will not add the margin to the final rendered width.
Using the box model and box sizing property will allow you to create well-spaced and responsive layouts.
Understanding how components like margin, border, padding, and content interact with each other is key to mastering CSS.

# Application of acquired knowldge

In application of the knowledge acquired, we are going to design a review section for a product.
Below are the HTML and CSS codes for the review section;

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="reviews.css" />
    <title>Reviews</title>
  </head>
  <body>
    <div class="review-card-container">
      <div class="review-card">
        <h3>Great Product</h3>
        <p class="rating">⭐⭐⭐⭐⭐</p>
        <p>
          This product exceeded my expectations. Its incredibly versatile and
          easy to use
        </p>
        <p>Ajika Angelo</p>
      </div>

      <div class="review-card">
        <h3>Highly recommended</h3>
        <p class="rating">⭐⭐⭐⭐⭐</p>
        <p>
          I have tried out very similar products but this one stands out. Worth
          every penny
        </p>
        <p>Orieda Pius</p>
      </div>

      <div class="review-card">
        <h3>Good Value</h3>
        <p class="rating">⭐⭐⭐⭐</p>
        <p>
          This product offers great features at a reasonable price. Minor
          improvements
        </p>
        <p>Nathan Onwang</p>
      </div>
    </div>
  </body>
</html>
```

## The CSS code

```css
.review-card-container {
  text-align: center;
}

.review-card {
  display: inline-block;
  width: 300px;
  margin: 0 10px;
  vertical-align: top;
  border: 1px solid #ccc;
  background-color: #f9f9f9;
  box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
  padding: 20px;
  margin-bottom: 20px;
}

.review-card h3 {
  margin-top: 0;
  font-size: 1.2em;
}

.review-card p {
  margin: 10px 0;
}

.rating {
  color: #ff9900;
  font-size: 1.5em;
}
```

From the above code snippet, `padding` property is used to create space inside the .review-card element, pushing the content away from the edges of the element.
The `margin` property is used to create space around each .review-card element, providing spacing between the card themselves.
The `border` property adds a border around each .review-card element, visually separating it from other elements.
The .review-card elements are set to `display: inline-block`. This allows them to align horizontally in a row similar to inline elements, while still maintaining their characteristics.

### Below is the output:

![](https://res.cloudinary.com/practicaldev/image/fetch/s--KqJ7aVjn--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ptxeqnd7evdsaftf6mtb.png)

The above output is responsive due the combination of CSS properties like flexible width and the default behavior of block-level and inline-block elements.

### Responsive illustration:

![](https://res.cloudinary.com/practicaldev/image/fetch/s--DKnAWmZR--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/4xjjckf6p1lcs1ygg8ly.png)

# Conclusion

As you have learnt, the box model in CSS defines how elements are displayed on the page and how they interact with other elements. Understanding block and inline elements and how to manipulate them is core to mastering CSS layouts. With practice, you will find yourself intuitively reaching for block or inline elements to achieve your desired layout results. Pay close attention to margin, border, and padding and how they affect the size and position of elements.

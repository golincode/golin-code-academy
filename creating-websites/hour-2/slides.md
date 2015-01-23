#Slide 1 : HTML Recap
--------------

- Tags are usually written with an opening, a close, and content inbetween.
```
<tag> Some witty and funny content. </tag>
```
- Can be nested
```
<div>
    <div>
    </div>
</div>
```
- Enclosing vs. Self Closing tags.
```
<div></div>
<img>
```
- Attributes
```
<a href="http://google.com" target="_blank">Link</a>
<img src="">
```

#Slide 2 : CSS Intro
--------------

- CSS stands for Cascading Style Sheet and affects the look of a web page. 
- According to the co-author of CSS, the 'Cascading' part means;
> "The process of combining several style sheets and resolving conflicts between them" ~Håkon Wium Lie

- CSS makes use of html attributes and the name of the element itself.
    - class 
    - id

- understanding these attributes is much easier if we think of elements on the page as items in a shop with barcodes and serial numbers.
- `class` is a way of identifying many elements, like a barcode on an item.
- `id` is a way to identify a unique element, like a serial number of an item. As such, it should only be used once on a web page.


#Slide 3 : CSS Syntax
--------------

- As a general rule, CSS usually has the element you're addressing, followed by {} ('Braces', or 'Curly Brackets').
- Any CSS code goes inside the braces.
- Americanise all your spelling.

#Slide 4 : CSS Selectors
--------------

- To access the individual elements, we can use the tag name
```
div {/** CSS code goes here **/}
```
- We can also use the tag's class, which we reference with a '.' before the class.
```
.something {}
```
- Additionally, we can use the tag's ID attribute, which is referenced with a #
```
#something-else {}
```

#Slide 5 : Measurements 
--------------

- Pixels (px) : Width in pixels. Standard measurement.
- Percentage (%) : Width in percentages of parent element. 
- Em (em) : Relative to element's font size.
- Rem (rem) : Relative to font size of root element.

#Slide 6 : Measurements 
--------------

- vw : Relative to 1% of the width of the viewport
- vh : Relative to 1% of the height of the viewport
- vmin : Relative to 1% of viewport's smaller dimension
- vmax : Relative to 1% of viewport's larger dimension

#Slide 7 Visibility
--------------

- Intuitively, affects the visibility of an element on a web page.
```
div {
    visibility : display; // This makes sure the element is shown on the page.
    visibility : hidden; // This hides the element visibly, but doesn't change the position of the element
}
```

#Slide 8 : Display 
--------------

 - Effects how the element is drawn to the page
```
div {
    display: none; //Both hides the element visibily, and removes it from the page.
    display: block; //Forces the element to act as if it were a block type of element.
    display: inline; //Forces the element to act as if it were an inline type of element.
    // Note, this is a non-exhaustive list, and just includes the most common properties.
}
```
#Slide 9 : The CSS Box Model
--------------

- The CSS Box Model is a set of instructions that the browser follows to make web pages look the same.

- The CSS Box Model consists of four main parts;
    - The content area, where content is shown.
    - The padding area, which is the section between the content and border.
    - The border area extends the padding and is the delimiter between inside and outside of the box.
    - Margin is outside of the box, and is never visible.


![The CSS Box Model](https://mdn.mozillademos.org/files/8685/boxmodel-(3).png)

#Slide 10 : Width 
--------------

The Content Area
- The content area is where the meat of the element is. Its' dimensions are set as the content-width and content-height labels in the infographic.

- To set the size, the `width` and `height` parameters are used.

- As the name suggests, this affects the width of the element. Usually measured in pixels, but more esoteric measurements can also be used.
```
div {
    width : 100px;
}
```

#Slide 11 : Height
--------------

- As the name suggests, this affects the height of the element. Usually measured in pixels, but more esoteric measurements can also be used.
```
div {
    height : 100px;
}
```

#Slide 12 : Padding
--------------

- The content area is extended to the eventual borders which surround it. It can have its' colour set, and its' size is set using the `padding` shorthand.

**padding**
```
div {
    //longhand way of setting padding
   padding-top : 20px;
   padding-right : 40px;
   padding-bottom: 20px;
   padding-left: 40px;
   
   //shorter way of setting padding
   //        top  right  bottom  left
   padding : 20px 40px   20px    40px;
   
   //even shorter way of setting padding
   //       top  sides
   padding: 20px 40px;
}
```

#Slide 13 : Border & Border Radius
--------------

The border area extends the padding area with the area containing the borders. It is the area inside the border edge, and its dimensions are the border-box width and the border-box height. This area depends of the size of the border that is defined by the border-width property or the shorthand border. Additionally, the radius of the border can also be defined.

```
div {
    //longhand way of setting border;
    border-top-width: 10px;
    border-right-width: 10px;
    border-bottom-width: 10px;
    border-left-width: 10px;
    
    //shorthand way of setting border width;
    border-width: 10px;

    //longhand border-style declaration
    border-top-style: dashed;
    border-right-style: solid;
    border-bottom-style: dotted;
    border-left-style: grooved;
    
    //shorthand border-style declaration
    border-style: solid;

    //longhand border-color declartion
    border-top-color: #FF69B4;
    border-right-color: #FF69B4;
    border-bottom-color: #FF69B4;
    border-left-color: #FF69B4;
    
    //shorthand border-color declaration
    border-color: #FF69B4;
    
    //shorthand border declaration
    border: 10px solid #FF69B4;
    
    //longhand border-radius declaration
    border-top-left-radius: 10px;
    border-top-right-radius: 10px;
    border-bottom-right-radius: 10px;
    border-bottom-left-radius: 10px;
    
    //shorthand border-radius declaration
    border-radius: 10px;
}
```

#Slide 14 : Margin
--------------

- The margin area extends the border area with an empty area used to separate the element from its neighbors. It is the area inside the margin edge, and its' dimensions are controlled with the `margin` property.
```
div {
    //longhand way
    margin-top : 20px;
    margin-right : 10px;
    margin-bottom : 20px;
    margin-left : 10px;
    
    //slightly shorter way
            top  right  bottom  left
    margin: 20px 10px   20px    10px;
    
    //shorthand way
            top  sides
    margin: 20px 10px;
}
```

#Slide 15 : Text Align
--------------

 - Sets the text positioning in the element
```
div {
    text-align: left; //starts the text on the left most section of the element
    text-align: right; //pushes the text across to the right hand most side of the element
    text-align: center; //aligns the text with the center of the element
    text-align: justify; //all lines are spaced-out such that the first word aligns with the left margin and last word with the right margin
}
```

#Slide 16 : Text Decoration
--------------

 - This text styling property is used to set underline, strikethrough or overline on text using the `text-decoration` property.
```
p {
    //underlines, overlines and strikes through respectively.
    text-decoration: underline;
    text-decoration: overline;
    text-decoration: line-through;
}
```

#Slide 17 : Font Color
--------------

 - To set the colour of the text, we use the `color` command. We hark back to the `Colours in CSS` section at this point;

```
p {
    // A nice hot pink.
    color : #FF69B4;
}
```

#Slide 18 : Next Week...
--------------
- MOAR CSS
- COLOURS
- FONTS
- LISTS

#Slide 19 : Questions
--------------

- U CAN HAZ QUESTIONS?
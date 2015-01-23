#CSS - 1/2
-------------


#CSS Syntax

-----------------------------------------------

##CSS : wat?
- CSS stands for Cascading Style Sheet and affects the look of a web page. 
- According to the co-author of CSS, the 'Cascading' part means;
> "The process of combining several style sheets and resolving conflicts between them" ~Håkon Wium Lie

- CSS makes use of html attributes and the name of the element itself.
    - class 
    - id

- understanding these attributes is much easier if we think of elements on the page as items in a shop with barcodes and serial numbers.
- `class` is a way of identifying many elements, like a barcode on an item.
- `id` is a way to identify a unique element, like a serial number of an item. As such, it should only be used once on a web page.

- The following HTML is a structure that we are going to be addressing with CSS.
```
    <div class="something">
        <div id="something-else">
            <a href="http://www.google.com/">Google</a>
        </div>
    </div>
```

##CSS: Syntax
- As a general rule, CSS usually has the element you're addressing, followed by {} ('Braces', or 'Curly Brackets').
- Any CSS code goes inside the braces.

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


#CSS: Specificity

----------------------------------

##It's a mouthful
- One problem we will run in to is if we only want to reference the innermost div of the two.

- Anything we put inside 
```
div {}
```
- will style all divs on the page, which is probably not what we want.
- Therefore, we have to be more _specific_ with our CSS.

One way of doing this is referencing a div with a specific id and/or class;
```
div.something {}

div#something-else {}
```
- This is a good start, and very good practice, but there is more.
We can also reference nested elements in CSS as follows;
```
div div{}
```
- This now references only a div inside another div, and is much more _specific_.
However, if we wanted to be even more _specific_, we could use a class or ID;
```
div #something-else{}
```
- This now references the element with id `something-else` which is inside a div.

##CSS Specificity: How do we know how specific we're being?
- We give weights to each selector type.
    - A normal element has weight `1`.
    - A class or attribute selector has weight `10`.
    - An ID has weight `1000`.

So, we can calculate as follows;
```
div {}
1 normal element
1 specificity.

div.something {}
1 normal element + 1 class
1 + 10 = 11 specificity

div#something-else {}
1 normal element + 1 id
1 + 1000 = 1001 specificity
```

Now for a more useful demonstration;
```
All of these access the same element, however their order is from least to most specific.

div div a {}
3 elements
3 specificity

div.something div a{}
3 elements + 1 class
3 + 10 = 13 specificity

div.something div#something-else a{}
3 elements + 1 class + 1 id + 1 partridge in a pear tree
3 + 10 + 1000 = 1013 specificity
```
Therefore, the last CSS rule will take precedence.

- If two rules share the same source and specificity, the later one is applied.
- Personally, i'm a fan of this specific image; [CSS Specificity](http://www.stuffandnonsense.co.uk/archives/images/specificitywars-05v2.jpg)


Good practice is to not nest more than 3 deep;
```
div.something div#something-else a {}
```
is about as deep as we should need to go.

#CSS Language

-----------------------------

- Broadly speaking there are two types of CSS vocabulary.
    - First type affects the page layout
    - Second type affects the appearance of the elements on the page


- CSS language is in american spelling. They refuse to spell things like `colour` correctly. This is important to remember in CSS.
- CSS language is usually written with the property we want to set first, with the value we want to set it to coming after a colon. After the value has been set, a semi-colon is required to 'confirm' the statement.
```
color : red;
```
- Colours in CSS can be specified using three main methods;
    - Their name (aliceblue, tan, teal etc. More [right here!](http://www.w3.org/TR/2003/CR-css3-color-20030514/#svg-color) ). Each colour has its' own name, which corresponds to a colour that the browser will understand.
    - Their hex value ( #fff, #11BB77 etc. More right [here](http://www.color-hex.com/color-names.html) ). Hexadecimal colours rely on using [hexadecimal counting](http://www.wikiwand.com/en/Hexadecimal) to create colours from their red, green and blue components. 
    - Their RGB value ( rgb(255, 23, 1) etc. More right [here](http://www.rapidtables.com/web/color/RGB_Color.htm) )is another way of specifying colours, but stead of using sixteen values, we have 255 values to play with (0-255).
    - The final way to specify colours is using an HSL colour space. It's a lot more complicated, and looks like this; ![HSL colour space](http://thelandofcolor.com/wp-content/uploads/2010/03/HSL-Cone-Graphic.jpg)

More information on that [here](http://www.wikiwand.com/en/HSL_and_HSV).

**General Note: If all following CSS examples were in actual stylesheets, then the last instance of the instruction would be the one that determined the element's style**

##The CSS Box Model
- The CSS Box Model is a set of instructions that the browser follows to make web pages look the same.

- The CSS Box Model consists of four main parts;
    - The content area, where content is shown.
    - The padding area, which is the section between the content and border.
    - The border area extends the padding and is the delimiter between inside and outside of the box.
    - Margin is outside of the box, and is never visible.


![The CSS Box Model](https://mdn.mozillademos.org/files/8685/boxmodel-(3).png)

###1. The Content Area
The content area is where the meat of the element is. Its' dimensions are set as the content-width and content-height labels in the infographic.

To set the size, the `width` and `height` parameters are used.

**width** - As the name suggests, this affects the width of the element. Usually measured in pixels, but more esoteric measurements can also be used.
```
div {
    width : 100px;
}
```

**height** - As the name suggests, this affects the height of the element. Usually measured in pixels, but more esoteric measurements can also be used.
```
div {
    height : 100px;
}
```
###2. The Padding Area
The content area is extended to the eventual borders which surround it. It can have its' colour set, and its' size is set using the `padding` shorthand.

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

###3. The Border
The border area extends the padding area with the area containing the borders. It is the area inside the border edge, and its dimensions are the border-box width and the border-box height. This area depends of the size of the border that is defined by the border-width property or the shorthand border. Additionally, the radius of the border can also be defined.

**border**
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

###4. The Margin Area
The margin area extends the border area with an empty area used to separate the element from its neighbors. It is the area inside the margin edge, and its' dimensions are controlled with the `margin` property.
**margin**
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


##CSS affecting layout

**visibility** - Intuitively, affects the visibility of an element on a web page.
```
div {
    visibility : display; // This makes sure the element is shown on the page.
    visibility : hidden; // This hides the element visibly, but doesn't change the position of the element
}
```

**display** - Effects how the element is drawn to the page
```
div {
    display: none; //Both hides the element visibily, and removes it from the page.
    display: block; //Forces the element to act as if it were a block type of element.
    display: inline; //Forces the element to act as if it were an inline type of element.
    // Note, this is a non-exhaustive list, and just includes the most common properties.
}
```

**text-align** - Sets the text positioning in the element
```
div {
    text-align: left; //starts the text on the left most section of the element
    text-align: right; //pushes the text across to the right hand most side of the element
    text-align: center; //aligns the text with the center of the element
    text-align: justify; //all lines are spaced-out such that the first word aligns with the left margin and last word with the right margin
}
```

##CSS affecting appearance

###Colour
In CSS, there are two types of colour that can be set; the colour of text, and the colour of the background of the page.

**color** - To set the colour of the text, we use the `color` command. We hark back to the `Colours in CSS` section at this point;

```
p {
    // A nice hot pink.
    color : #FF69B4;
}
```

**background** - To set the background of the element, we would use the `background` shorthand property.
```
div {
    //background colour longhand
    background-color: #FF69B4;
    
    //background colour shorthand
    background: #FF69B4;
}
```
- We can also set images as the background with the `background` shorthand property.
```
div {
    //background image longhand
    background-image: url("http://golin.com/uk/wp-content/uploads/2014/10/2014-PR-Week-selfie2.jpg");

    //background image shorthand
    background: url("http://golin.com/uk/wp-content/uploads/2014/10/2014-PR-Week-selfie2.jpg");
}
```

###Fonts
**font-family** - As you've seen in your word processor that you're familiar with, there are many fonts that you can select to add flavour to your text. HTML is little different; in HTML, however, we use the "font-family" parameter.
```
p {
    //We sequentially specify fonts that we hope the user has on their computer, until we get to a universal font.
    font-family: Helvetica, Arial;
    
    //We can also specify a type of font to use.
    font-family: serif; //uses the first 'serif' font found on the system. Think 'Times New Roman'.
    font-family: sans-serif; //uses the first 'sans-serif' font found on the system. Think 'Arial'.
    font-family: cursive; //uses the first 'cursive' font found on the system.
}
```

**font-size** - Again, as in your word processor, you can specify the size of the font. In CSS, you would use the `font-size` parameter.
```
p {
    font-size: 12px;
}
```

**font-weight** - This is something you might not have seen in your word processing. Here we can specify how bold we want the font to be, with numbers or words.

```
p {
    font-weight: lighter;
    font-weight: normal;
    font-weight: bold; 
    font-weight: bolder;
    
    font-weight: 100;
    font-weight: 200;
    font-weight: 300;
    font-weight: 400;
    font-weight: 500;
    font-weight: 600;
    font-weight: 700;
    font-weight: 800;
    font-weight: 900;
}
```

**text-decoration** - This text styling property is used to set underline, strikethrough or overline on text using the `text-decoration` property.
```
p {
    //underlines, overlines and strikes through respectively.
    text-decoration: underline;
    text-decoration: overline;
    text-decoration: line-through;
}
```

AMRoche, 2015
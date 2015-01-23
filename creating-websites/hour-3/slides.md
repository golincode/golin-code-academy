#Slide 1 : A CSS Recap
--------------

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

- We can also reference nested elements in CSS as follows;
```
div div{}
```
- This now references only a div inside another div, and is much more _specific_.
However, if we wanted to be even more _specific_, we could use a class or ID;
```
div #something-else{}
```

#Slide 2 : Background: color
--------------

- To set the background of the element, we would use the `background` shorthand property.
```
div {
    //background colour longhand
    background-color: #FF69B4;
    
    //background colour shorthand
    background: #FF69B4;
}
```

#Slide 3 : Background: image - Demo Only
--------------

- We can also set images as the background with the `background` shorthand property.
```
div {
    //background image longhand
    background-image: url("http://golin.com/uk/wp-content/uploads/2014/10/2014-PR-Week-selfie2.jpg");

    //background image shorthand
    background: url("http://golin.com/uk/wp-content/uploads/2014/10/2014-PR-Week-selfie2.jpg");
}
```

#Slide 4 : Background: gradient - Demo Only
--------------

 - Ever wanted to fade one colour to another? Well, CSS has got you covered!
We can make gradients by making use of the `background-image` property of an element. If you 
are wanting a more [Photoshop like](http://www.colorzilla.com/gradient-editor) interface,
well we can automatically generate the gradient. This is important as usually gradients need
the browser prefixing we saw earlier. More information
[right here](http://css-tricks.com/css3-gradients/) along with more examples and uses.

```
#importantElement {

    background-color: red;

/**
    background-image: linear-gradient(
        <where we want it to go>, //not necessary, more information at link above
        <colour> <colour stop>,
        <colour> <colour stop>
    );
    
    background-image: radial-gradient(
        <where we want it to go>, //not necessary, more information at link above
        <colour> <colour stop>,
        <colour> <colour stop>
    );
**/

    background-image: linear-gradient(
      to top right, 
      red,
      #f06d06
    );
    
    background-image: linear-gradient(
      to top right, 
      red 50%, //red to 20% of the way across, and then ...
      yellow //YELLOW!
    );
}
```

#Slide 5 : Font Family
--------------

 - As you've seen in your word processor that you're familiar with, there are many fonts that you can select to add flavour to your text. HTML is little different; in HTML, however, we use the "font-family" parameter.
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

#Slide 6 : Font Size
--------------

- Again, as in your word processor, you can specify the size of the font. In CSS, you would use the `font-size` parameter.
```
p {
    font-size: 12px;
}
```
#Slide 7 : Font Weight
--------------

 - This is something you might not have seen in your word processing. Here we can specify how bold we want the font to be, with numbers or words.

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

#Slide 8 : Line Height
--------------

 - This property affects the text, and is the last element
concerning text we're going to cover. Again, this takes most of its' cues from
the days of a printing press. Whichever value you specify is split equaly and 
added to the top and bottom of the text.

```
#importantElement {
    line-height: 20px; //adds ten pixels to the top and bottom
    line-height: 150%; //adds 75% of the font size to the top and bottom
    line-height: 2; //adds 1 times the font size to top and bottom
    line-height: normal; //lets the browser decide which is best
    line-height: inherit; //gets the line height from further up the document tree
}
```

#Slide 9 : Text-Transform
--------------

 - Allows us to target specific elements and change
how the text of the element looks.

```
#importantElement {
    text-transform: capitalize;
    text-transform: uppercase;
    text-transform: lowercase;
    text-transform: none;
    text-transform: inherit;
}
```

#Slide 10 : List Style
--------------

 - We covered lists in the opening HTML hour, and this CSS key
is used to style the bullet points associated with Lists. Is also shorthand
for separate _list-style_ commands.


```
#importantElement {
    list-style: <type> <position> <image>; //is shorthand for these declarations;
    
    list-style-type: none; //so very many.
    list-style-position: inside; //or 'outside'.
    list-style-image: url(''); //or none.
}
```

List Style Types; disc, circle, square, decimal, decimal-leading-zero, lower-roman, upper-roman, lower-greek, lower-latin, upper-latin, armenian, georgian, lower-alpha, upper-alpha, none


#Slide 11 : Box Shadow: Demo Only
--------------

 - Floating objects are cool, right? How about making your entire 
web page float? Aww yeah. Can be used for anything that is a block level element.

```
#importantElement {
    box-shadow: 
        <horizontal offset>
        <vertical offset>
        <blur radius>
        <spread> 
        <colour>;
        
    box-shadow: 3px 3px 5px 6px fuchsia;
}
```
![Image of Box Shadow](http://www.funnygarbage.com/sites/default/files/images/all_around.jpg)

- The _horizontal offset_ of the shadow. A positive value will have the shadow 
on the right side of the box, while a negative will place it on the left.
- The _vertical offset_ of the shadow. Same as _horizontal offset_, just up and
down instead of left and right.
- The _blur radius_ (optional, px). How much blur to apply to the shadow
(0px is the lowest value).
- The _spread radius_ (optional, px). Shadow size; positive numbers make it larger,
negative make it smaller. It defaults to zero, which makes it the same size as the blur.

What we can also do with a box shadow is add a parameter to the beginning called **inset**.
What this will do is move the shadow from _outside_ the element to _inside_ the element.

#Slide 12 : Css Animations: Demo Only
--------------

 - Yes, animations in CSS are a thing that you can do.
Much more information [right here](http://css-tricks.com/almanac/properties/a/animation/) .
These can be comma separated if you want to include multiple animations. We need to include
browser prefixes so the animations work in each browser properly.
```
#importantElement {
/**
    animation:
        <name of animation> Pick a name without spaces
        <duration> s or ms
        <delay> s or ms
        <how many times to loop> infinite, or a number
        <fill mode> forwards, backwards, both, none
        <animation direction>; normal, alternate
**/

    -webkit-animation: bounce 1s infinite;
    -moz-animation:    bounce 1s infinite;
    -o-animation:      bounce 1s infinite;
    animation:         bounce 1s infinite;
}
```

So, now we have the animation declared, we need to write the actual animation.
This is done using Keyframes. Imagine keyframes as the images that are part of a film.
We can use 'from' and 'to' to define how we want the elements to change.

```
@keyframes bounce {
  from {
    font-size: 10px;
  }
  
  to {
    font-size: 20px;
  }
}
```

However, as you can see, this is not enough for a bounce. We only have two points!
Luckily, we can also use percentages to define these.

```
@keyframes bounce {
  0% {
    font-size: 10px;
  }
  
  25%, 75% {
    font-size: 15px; 
  }
  
  50% {
    font-size: 20px;
  }
  
  100% {
    font-size: 10px;
  }
}
```

We also need browser prefixes for the animation definitions.

```
@-webkit-keyframes bounce {
  0% {
    font-size: 10px;
  }
  
  25%, 75% {
    font-size: 15px; 
  }
  
  50% {
    font-size: 20px;
  }
  
  100% {
    font-size: 10px;
  }
}

@-moz-keyframes bounce {
  0% {
    font-size: 10px;
  }
  
  25%, 75% {
    font-size: 15px; 
  }
  
  50% {
    font-size: 20px;
  }
  
  100% {
    font-size: 10px;
  }
}

@-o-keyframes bounce {
  0% {
    font-size: 10px;
  }
  
  25%, 75% {
    font-size: 15px; 
  }
  
  50% {
    font-size: 20px;
  }
  
  100% {
    font-size: 10px;
  }
}

@keyframes bounce {
  0% {
    font-size: 10px;
  }
  
  25%, 75% {
    font-size: 15px; 
  }
  
  50% {
    font-size: 20px;
  }
  
  100% {
    font-size: 10px;
  }
}
```

#Slide 13 : Float: Demo Only
--------------

- The origin of this property is in print design, where an image (or other elements)
can be set on a page such that text will wrap around them as needed, which is commonly called _text wrap_.

![http://css-tricks.com/wp-content/csstricks-uploads/print-layout.png](http://css-tricks.com/wp-content/csstricks-uploads/print-layout.png)

In this layout, text can be told to either honor the text wrap, or completely ignore it.
The same is true when using CSS.

Setting the layout is, again, a case of using the property's name with a value.
```
#importantElement {
    float: left; //moves the element as far left as possible in its' containing element.
    
    float: right; //moves the element as far right as possible in its' containing element.
    
    float: none; //removes any float set. Mostly used to override other conflicting classes.
    
    float: inherit; //As this is a 'child' element, it gets the float from the parent.
}
```

#Slide 14 : clearfix
--------------

 - Floats are all good, and super useful, right? Yes, but they can also
do evil things if you're not careful. The issue here is that if there's no visible background
you might not even notice it.

The issue is that if all of your content elements are floated, then the wrapping container's
height will drop to zero, which can be a serious issue.

![collapsed div](http://css-tricks.com/wp-content/csstricks-uploads/collapse.png)

There is however a way to save this situation!

Enter the _clearfix_

**Cleafix** - uses a clever CSS selector to clear floats.
You apply an additional class like "clearfix" to it, with the following CSS;

```
.clearfix:after { 
   content: "."; 
   visibility: hidden; 
   display: block; 
   height: 0; 
   clear: both;
}
```

This will apply a small bit of content, hidden from view, after the parent
element which clears the float.

#Slide 14 : Next Week
--------------
- T3h wordPressz0orz

#Slide 15 : Questions
--------------
- U CAN HAZ QUESTIONS?
#CSS - Hour 2

-------------------------

##CSS Syntax, a recap.
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

##CSS syntax++

**Attribute Targeting** - Elements can be targeted not only on classes or id's, but also on any other attribute.
For this example, we'll use the following HTML;

```
<a href="www.google.com" target="_blank">Google</a>
<a href="www.golin.com">Google</a>
<a href="www.google.com" target="">Google</a>
```

This is HTML that can then be targeted thusly;
```
a {
    color: fuchsia;
    text-decoration: overline;
}

a[target="_blank"] {
    color: red;
    text-decoration: none;
}

a[target] {
    color: pink;
}
```
This will result in the link which has the `target` attribute set to `_blank` being coloured red, and the standard underline for links being removed, with the normal link being coloured fuchsia and an overline added. The last link would have its' text set to pink colour, as it has a 'target' attribute.

**Advanced Selectors** - Up until now, we've only been using linear descendents in our CSS. However, this isn't all that's possible in CSS. The following are a few of the most useful advanced selectors, with a lot more being on [this website](http://code.tutsplus.com/tutorials/the-30-css-selectors-you-must-memorize--net-16048).

** * selector ** - This selector will select everything. Literally everything. No messing around here.

HTML :
```
<div>
    <ul>
        <li>
            <ul>
                <li></li>
            <ul>
        </li>
        <li></li>
    </ul>
    <span></span>
    <p></p>
</div>
```
CSS :
```
div * {
    // Any styles in here will be applied to the 'ul', 'span' and 'p' tags. 
}
```
** + selector ** - This selector is called the 'adjacent' selector. It will select only the element that is immediately preceded by the former element.

Using the HTML from the previous example with this CSS gives us;
```
div ul + li {
    //This CSS will only target the first li element of the ul.
}
```

** ~ selector ** - This selector is a sibling selector, and is similar to the adjacent selector.
```
    div ul + li {
        //This CSS will only target the first li element of the ul.
    }
    
    div ul ~ li {
        //This CSS will target all li elements in the first ul
    }
```

** > selector ** - This selector is the direct child selector.

```
div ul {
    //this CSS would style both of the UL elements above.
}

div > ul {
    //this CSS, however, would only style the first UL.
}
```

##Layout++

**overflow** - Imagine this; you're writing on a page and you only have limited paper.
Everything has to fit in the space you've been given, and you can't overrun. How do you do this in CSS?

```
#element {
    overflow: visible; // displays the text overflow no matter what.
    overflow: hidden; // hides the text overflow no matter what.
    overflow: scroll; // adds scroll bars to the content element. 
    overflow: auto; // adds content scroll bars as and where they're necessary.
}
```

There are also directional overflow properties, which are less uncommon; _overflow-y_ and _overflow-x_.
These both have the same properties as _overflow_, just _overflow-y_ refers to vertical overflow,
whereas _overflow-x_ refers to horizontal overflow.

**position** - As you might think, this specifies how the element is positioned on the page.

```
#importantElement {
    position: static; //default, only use this if you're overriding a different styling.
    
    position: relative; //Element's original position remains in the document, 
                        //but is now 'nudged' in specified direction.
                        
    position: absolute; //Element is removed from the flow of the document, letting the user 
                        //specify the exact position you want it to have.
                        
    position: fixed; //Just like absolute, but relative to document instead of a parent element
    
    position: inherit; //As this element is a 'child', we get the property from the containing element
}
```

Now, one necessary part of this that we haven't mentioned is how we go about 'nudging' the elements around.
We use four properties, namely _top_ , _right_, _bottom_ and _left_.
```
#importantElement {
    position: absolute; //Just like absolute, but relative to document instead of a parent element
    
    bottom: 5px; //Can be any value of size accepted by CSS.
    left: 5px; //Again, can be any value of size accepted by CSS.
}
```
This then results in the following;

![This would then give is the following](http://cdn.css-tricks.com/wp-content/uploads/2012/03/positionabsolute.png)

As you can see, the distance values that we have passed in reference distance from the _side referenced_.

**float** - The origin of this property is in print design, where an image (or other elements)
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

**clear** - This is a sister property of float. An element that has the _clear_ property
set on it will not move up next to the floated element, but will move itself down past
the float.

![Non-cleared image](http://css-tricks.com/wp-content/csstricks-uploads/unclearedfooter.png)

This is the result of three elements, two of which have been floated in opposite directions.
We usually want the footer at the bottom of the page, so, to this end we can use the _clear_
parameter.

```
#footer {
    clear: both; //used to clear elements that have either float: right or float: left.
    
    //clear: left; //used to clear elements that are floated left.
    
    //clear: right; //this is used to clear elements that are floated right
    
    //clear: none; //this is used to re-set an element to a non-cleared state.
}

```

This will then result in the following;

![Cleared image](http://css-tricks.com/wp-content/csstricks-uploads/clearedfooter.png)

**Div Collapse** - Floats are all good, and super useful, right? Yes, but they can also
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

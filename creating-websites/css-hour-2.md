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
    //this CSS, however, would only style the forst UL.
}
```

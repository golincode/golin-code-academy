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

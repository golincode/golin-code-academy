#HTML
--------
##A 'Brief' history

- late 1960's - First connection between two computers
Couldn't transmit three characters before falling over
- 1970 - 1990 - Merging networks to start to form the internet as we know it.
- Due to differing standards, networks needed to be patched together, which took
a few years. Imagine what happens whenever you go abroad and need different plugs; similar thing.
- 1989 - Radically innovated by Tim Berners Lee at CERN with HTML.
- First example of a webpage as we currently understand them
- 1989 - 2010 - Global standardisation and connection
- 1996 - Google
- 2004 - Facebook & Fuse (Now Architect)
- 2005 - YouTube
- 2006 - Twitter
- 2015 - Cat Gifs.
- The first website's HTML code; 
![First Website](https://s3.amazonaws.com/media-p.slid.es/uploads/alexroche/images/927126/Screen_Shot_2014-12-12_at_16.07.17.png)
How the first website looked;
![First Website II](https://s3.amazonaws.com/media-p.slid.es/uploads/alexroche/images/927124/Screen_Shot_2014-12-12_at_16.03.56.png)

##HTML Standards

- Each change is reviewed by a standards committee called the W3C (World Wide Web Consortium)
- Benefits from wide review
- Can take many years to finalise
- Has many stages
	- Working Draft
	- Candidate Recommendation
	- Proposed Recommendation
W3C Recommendation
Gives a good indication what web professionals want to happen

##What is HTML?

- Stands for HyperText Markup Language
- A standardised method of building web pages
- Consists of tags such as these :
```
<p></p>
<img>
```
- Each tag wraps around content to produce the desired effect
- Each tag has meaning and a reason to use it
- .html is the most common file extension for html files
- Browsers automatically recognise .html files
- Main site pages are usually named 'index'
	- This is a convention that is automatically recognised by the server
	- Can be changed on the server

##How is HTML?

###Text Editor
- \+ Can be any text editor
- \+ Gives you more control over the web page
- \+ Usually very extensible and customisable


- \- Won't be visible until the file is accessed in the browser
- \- Everything must be hand coded
- \- Knowledge of HTML, CSS and Javascript required

###WYSIWYG Editor (What You See Is What You Get)
- \+ Manages all of the files and styling for you
- \+ Website is visible in the program itself
- \+ Doesn't need knowledge of HTML
 

- \- Reliance on editor creating good markup
- \- Not very customisable
- \- Is a specific kind of software

##HTML code

###What are tags?
- Tags are usually written with an opening, a close, and content inbetween.
```
<tag> Some witty and funny content. </tag>
```

- Can be nested (Put inside eachother)
- Describes the structure of a web page
- HTML tags come in all kinds of flavours
- Text : **Bold**, #Heading, [Link](https://www.youtube.com/watch?v=BROWqjuTM0g), _Emphasised_, Superscript etc.
- Formatting : Paragraph, Lists
- Tags like : Body, Header, Footer all have a proper meaning, and should only be used in the correct place.

###General Knowledge;

- Creating a heading. We use the heading tag name (h1) and stick it inside <>.
Once we've finished the tag, we close it with a / and the tag name, again inside <>
```
<h1> Golin Weekly - The latest news from the PR world at Golin London </h1>
```

- Creating a smaller heading. There are six(!) heading types in all; h1, h2, h3, h4, h5 and h6.
- h1 is the largest heading, and h6 is the smallest heading.
```
<h3> Decorating for Christmas at Golin! </h3>
```
- _Emphasising_ Text
```
<em> whole office </em>
```

- Creating a paragraph of text.
```
<p> 
	Decorating for Christmas at Golin was fun, with the whole office getting involved.
</p>
```

- Nesting tags; we can just stick tags inside other tags.
```
<p> 
    Decorating for Christmas at Golin was fun, with the
    	<em>
    		whole office
    	</em>
    getting involved.
</p>
```

- Grouping the text together in a logical block
```
<div>
    <h3> Decorating for Christmas at Golin! </h3>
    <p> 
        Decorating for Christmas at Golin was fun, with the 
        	<em> 
        		whole office 
        	</em>
        getting involved.
    </p>
</div>
```

Now that we know this, we can create our first article;

```
<div>
	<h3> Decorating for Christmas at Golin! </h3>

        <a href="http://www.wikipedia.org/en/Christmas"

    	    <img 
                src="http://upload.wikimedia.org/wikipedia/commons
                    /f/f2/Christmas_Wreath_-_geograph.org.uk_-_639554.jpg" 
                alt="A Christmas Wreath"
            />

    	</a>

        <p> 
	    Decorating for Christmas at Golin was fun, with the <em> whole office </em>
	    getting involved. <a href="/gallery"> Click here </a> for a look at the photos.
	</p>
</div>
```
This will be inserted in to the web page later.

### The anatomy of a website

- A web page can be very simple, as already shown
**HOWEVER**
- A webpage also needs semantic context.
- This is accomplished by using some distinguishing tags
	- ```<!DOCTYPE html> ```
	- ```<html></html>```
	- ```<head></head>```
	- ```<body></body>```
- Once the main document is laid out, we use tags to group content.
	- ```<div></div>```
	- ```<span></span>```

###Setting out the web page

- First, we set out an HTML document :
```
<!DOCTYPE html>
<html>
    <head>
    </head>
    <body>
    </body>
</html>
```

- Then we can insert some content in to the page :
```
<!DOCTYPE html>
<html>
    <head>
        <title>
        	Golin PR Week - a demo website for the Golin Code Academy
        </title>
    </head>

    <body>
        <div>
            <h3> Decorating for Christmas at Golin! </h3>
            <p> 
                Decorating for Christmas at Golin was fun, with the <em> whole office </em>
                getting involved.
            </p>
        </div>
    </body>
</html>
```

###What are attributes?

- Tags can also have properties called 'attributes'
- These additional attributes add functionality
- Enables us to;
	- Link to other parts of the web
	- Insert images in to the document
	- Insert metadata for the document
	- Add styling to specific elements
	- Reference elements specifically when writing styles

Adding an attribute is achieved as follows;
```
<tag attribute="value">Content of our tag</tag>
```

You can have many attributes in a tag, which is what we do when we create images;
```
<img src="" width="" height="">
```

We also have attributes if we are trying to add a reference for when we get around 
to styling the page;

```
<div id="important-styling-reference" class="styling-reference">
</div>
```

###Self Closing Tags
- Tags don't always have to have a closing tag, and are known as self-closing.
Some examples of this include;
	- doctype
	- img
	- link
	- meta
	- script

Usually used in conjunction with attributes, such as an image tag;
```
<img src="http://goo.gl/aUK461" alt="Good News, Everyone!" />
```

_**Note:** it is both impossible and ill advised to try putting a different tag inside a self closing tag.
Everything will break._

###Meta Data for the Document
- This will make the document more visible on search engines and in browsers
- Meta elements are tags used in HTML or XHTML documents to provide structured metadata about a Web page.
- They are part of a web page's head section.
- Multiple Meta elements with different attributes can be used on the same page.
```
    <head>
        <title>Golin PR Week - a demo website for the Golin Code Academy</title>
		<meta charset="utf-8">
        <meta name="keywords" content="PR, Design, Go All In, Golin">
        <meta name="author" content="David Hasselhoff">
    </head>
```

###Two different types of content containers
- HTML tags come in two main types
	- Block tags
	- Inline tags
- Block tags take up the full width available, with a new line before and after.
In short, they stack up horizontally and sit under eachother neatly.
- ```​<div></div>```, ```<p></p>``` & ```<h></h>```
- Inline tags take up only as much width as they need, and do not force new lines 
- ​```<span></span>```, ```<a></a>```, ```<img/>```, ```<em></em>```
- Both block and inline tags' behaviour can be changed using external styling

![Element Things](http://netdna.webdesignerdepot.com/uploads/2012/08/boxmodel-block-vs-inline.png)

### Lists; ordered vs. unordered.
- A number of connected items or names written or printed consecutively, typically one below the other
**OR**
- "What is there to describe, they're a fucking list; it's not a hard concept" ~ Gareth Bishop
- Two types of list
	- Ordered
	- Unordered
- Just like in a word processing program :
![Lists](https://s3.amazonaws.com/media-p.slid.es/uploads/alexroche/images/936975/Screen_Shot_2014-12-16_at_14.09.05.png)


**Ordered Lists**
![Ordered List](https://s3.amazonaws.com/media-p.slid.es/uploads/alexroche/images/936995/Screen_Shot_2014-12-16_at_14.14.57.png)
```
<ol>
    <li> <a href="www.golin.com/uk/">Golin.co.uk</a> </li>
    <li> <h1> <a href="/"> home </a> </h1> </li>
    <li> <h1> <a href="/"> gallery </a> </h1> </li>
</ol>
```

**Unordered List**
![Unordered List](https://s3.amazonaws.com/media-p.slid.es/uploads/alexroche/images/937005/Screen_Shot_2014-12-16_at_14.20.13.png)
```
<ul>
    <li> <a href="www.golin.com/uk/">Golin.co.uk</a> </li>
    <li> <h1> <a href="/"> home </a> </h1> </li>
    <li> <h1> <a href="/"> gallery </a> </h1> </li>
</ul>
```

Now we've covered lists, we can add a navigation bar to our web page;
```
<div>
	<ul>
		<li><a href="/">Home</a></li>
		<li><a href="/about">About</a></li>
		<li><a href="/news">News</a></li>
		<li><a href="/views">Views</a></li>
		<li><a href="/showcase">Showcase</a></li>
	</ul>
</div>
```

## HTML5 goodness
- HTML5 has introduced a new set of tags which gives extra meaning to the elements.

```
<nav></nav>
```
- Site or in-page navigation

```
<article></article>
```
- Used with news article, Blog or Forum post, or as asidebar widget

```
<figure></figure>
```
- Used for one or more images, graphics, code samples
- Used with an optional ``` <figcaption></figcaption>```

 ```
 <aside></aside>
 ```
- Used as a sidebar, comments section, glossary, advertising, footnote

 ```
 <section></section>
 ```
- Used for a section of page or chapter of an ``` <article></article>```


Now, we change our nav bar to be wrapped in _nav_ tags instead of _div_ tags.
```
<nav class="global-navigation">
	<ul>
		<li><a href="/">Home</a></li>
		<li><a href="/about">About</a></li>
		<li><a href="/news">News</a></li>
		<li><a href="/views">Views</a></li>
		<li><a href="/showcase">Showcase</a></li>
	</ul>
</nav>
```

Next, we change our articles and wrap them in the correct tags; section and article.
Again, before HTML we would have used _div_ tags for this.
```
<section>
    <article>
    	<h3> Decorating for Christmas at Golin! </h3>
    		<a href="http://www.wikipedia.org/en/Christmas"
    			<img 
    				src="http://upload.wikimedia.org/wikipedia/commons
    					/f/f2/Christmas_Wreath_-_geograph.org.uk_-_639554.jpg" 
    				alt="A Christmas Wreath"
    			/>
    		</a>
    		<p> 
    		Decorating for Christmas at Golin was fun, with the <em> whole office </em>
    		getting involved. <a href="/gallery"> Click here </a> for a look at the photos.
    	</p>
    </article>
</section>
```

Now, we will make use of the _aside_ tag for some blurbs for other articles.
```
<div>
	<aside>
		<h2>Latest gossip</h2>

		<h3>Something something something</h3>
		<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolorem quo, velit eos porro aperiam possimus exercitationem.</p>

		<h3>Something something something</h3>
		<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolorem quo, velit eos porro aperiam possimus exercitationem.</p>

		<h3>Something something something</h3>
		<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolorem quo, velit eos porro aperiam possimus exercitationem.</p>

		<a href="#">More gossip!</a>
	</aside>
</div>
```

Once we've made all of these changes, we end up with the following page;
```
<!DOCTYPE html>
<html>
	<head>
		<title>Golin PR Week - a demo website for the Golin Code Academy</title>
		<meta charset="utf-8">
		<meta name="keywords" content="PR, Design, Go All In, Golin">
		<meta name="author" content="David Hasselhoff">
	</head>
	<body>
		<div> <!-- General containing element for page -->
		<nav class="global-navigation">
			<ul>
				<li><a href="/">Home</a></li>
				<li><a href="/about">About</a></li>
				<li><a href="/news">News</a></li>
				<li><a href="/views">Views</a></li>
				<li><a href="/showcase">Showcase</a></li>
			</ul>
		</nav>
		<section>
			<article>
			<h3> Decorating for Christmas at Golin! </h3>
			<a href="http://www.wikipedia.org/en/Christmas"
			<img
			src="http://upload.wikimedia.org/wikipedia/commons
			/f/f2/Christmas_Wreath_-_geograph.org.uk_-_639554.jpg"
			alt="A Christmas Wreath"
			/>
			</a>
			<p>
			Decorating for Christmas at Golin was fun, with the <em> whole office </em>
			getting involved. <a href="/gallery"> Click here </a> for a look at the photos.
			</p>
			</article>
		</section>
		<div>
			<aside>
				<h2>Latest gossip</h2>
				<h3>Something something something</h3>
				<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolorem quo, velit eos porro aperiam possimus exercitationem.</p>
				<h3>Something something something</h3>
				<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolorem quo, velit eos porro aperiam possimus exercitationem.</p>
				<h3>Something something something</h3>
				<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolorem quo, velit eos porro aperiam possimus exercitationem.</p>
				<a href="#">More gossip!</a>
			</aside>
		</div>
	</div>
</body>
</html>
```
![NEW PAGE](https://s3.amazonaws.com/media-p.slid.es/uploads/alexroche/images/937221/Screen_Shot_2014-12-16_at_15.17.38.png)

Next week we will focus on styling this up using [Cascading Style Sheets](http://www.wikiwand.com/en/Cascading_Style_Sheets)
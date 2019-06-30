---
layout: post
title:      "Getting Friends with CSS"
date:       2019-06-30 08:54:57 +0000
permalink:  getting_friends_with_css
---


Resently I've been thrown in the ocean with a tight dead line and almost no help on a project of styling a static web page to match a fancy design created by a graphic expert. Knowing little about css, I could not even estimate what a learning curve it would be! 

I'd like to share some tips and trics I've learned from my experience. I wish they were explained in many tutorials I watched - that would save me tons of time and stress. 



### Trick#1. Red Borders to the Resque

Guessing all padding,  marging, positions and sizing could give you are great misery - trust me, I've been there. To save yourself sanity simply use this short jQuery in console. It realy does the magic!

```

$( "*" ).css( "border", "3px solid red" )

```

A caution for experts: The all, or universal, selector is extremely slow, except when used by itself.


 
### Trick#2. Font is a shorthand property

“Font” is a CSS shorthand property. Therefore, instead of writing all properties, you can just combine them all under one:

```
h1 {
 font-weight: bold;
 font-style: italic;
 font-size: 1rem;
 //etc…
}
// vs
h1 {

 font: italic lighter 1rem/150% Verdana, Helvetica, sans-serif;
}
// syntax
// font: font-style font-variant font-weight font-size/line-height font-family;
```



### Trick#3. @supports for checking browser support

You can use @supports feature query to check for browser support. As an example: if you wish to use “display:flex” only when it’s actually supported you can set it up like so:

```
@supports (display: flex) {
 div {
   display: flex;
 }
}
```


### Trick#4. Lobotomized owl selector

[Lobotomized owl selector](https://alistapart.com/article/axiomatic-css-and-lobotomized-owls/) is the one to know for both using and reading someone's code:
 
```
* + * {
 margin-top: 2rem;
}
```

Useful for situations when you have multiple elements of the same kind that need some spacing, for example list or nav link items.

```
li + li {
 margin-top: 1rem;
}
// vs
li {
 margin-bottom: 1rem;
}
li:last-of-type {
  margin-bottom: 0;
}
```

### Trick#5. Margins overlap, but only sometimes

So space between the following elements will be 20px, not 40px:

```
<div style="margin-bottom:20px">foo</div>
<div style="margin-top:20px">foo</div>
```

However, there are exceptions! The margins don’t collapse in the following circumstances:
floated elements
* absolutely positioned elements
* inline-block elements
* elements with overflow set to anything other than visible (they do not collapse margins with their children.)
* cleared elements (They do not collapse their top margins with their parent block’s bottom margin.)
the root element

### Trick 6. Opacity can change the z-index stacking order

Say you have 3 divs, each positioned absolutely, containing another element with increasing z-index number. Each next one will appear on top of the previous one. If you add z-index: 10 to the first one, it will now appear on top of the other two, which remain ordered as before. So far all good. Now add “opacity: 0.99” to the first div and watch it get stacked under the other two. :)

```
//HTML

<div id="ontop" >
  <span class="red">z-index:10</span>
</div>
<div>
  <span class="green">z-index:2</span>
</div>
<div>
  <span class="blue">z-index:1</span>
</div>

<button id="foo">Add "opacity:0.99;" to red div</button>


//css
/* #ontop {
  opacity: .99; 
} */

.red, .green, .blue {
  position: absolute;
  width: 100px;
  color: white;
  line-height: 100px;
  text-align: center;
}
span {
  opacity: .95;
}

.red {
  z-index: 10;
  top: 20px;
  left: 80px;
  background: red;
}

.green {
  z-index: 2;
  top: 80px;
  left: 20px;
  background: green;
}

.blue {
  z-index: 3;
  top: 100px;
  left: 100px;
  background: blue;
}

button {
  position: absolute;
  top: 230px;
}

//js
document.getElementById('foo').onclick = function(){    
    document.getElementById('ontop').style.opacity = '0.99';
}

```

### Trick#7. Height: 100% may not do what you think it does

Same goes for “height: 100%”, in many cases this does not do what the developer expects, because parent element’s height is not set. So for example:

```
<html>
<body>
  <div style=”height:100%;background:red;”></div>
</body>
</html>
```

This does not fill the whole page red. In order to do that, you’d need to set the height of both body and html to 100%.

More to find [here](https://medium.com/@peedutuisk/lesser-known-css-quirks-oddities-and-advanced-tips-css-is-awesome-8ee3d16295bb).

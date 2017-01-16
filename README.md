# SASS & SCSS:
##An introduction to Syntactically Awesome Style Sheets and Sassy Cascading Style Sheets

###Introduction:

SASS and SCSS, or Syntactically Awesome Style Sheets and Sassy Cascading Style Sheets, are not web page frameworks (Like Bootstrap or Materialize for HTML), and they're not libraries built on top of existing languages (like jQuery for Javascript)... So what are they?

The terms SASS and SCSS are used somewhat interchangeably by the developer, however they have slight differences. "SASS", as the front-end developer/blogger Nick (yes, just Nick) explains, "refers to the preprocessor and syntax as a whole," while "SCSS falls under the umbrella of SASS." He continues, "[SASS] is a CSS syntax that's been turbocharged with all the goodness of SASS." Andrew Chalkley from Team Treehouse adds that "SCSS looks more like what you’re used to with CSS, but it has 'Sassy' features like variables, mixins, nesting and selector inheritance."

What is a preprocessor you ask? Again, we refer to our tutor Nick, who tells us that "preprocessors are tools that allow us to code CSS in a certain way, and process it into readable, pure CSS." Specifically, they compile (or, for the purposes of this tutorial, translate) from SASS into the same exact language as CSS.

Sounds pretty good to me, but...

###Why do we care?

For those of you that are familiar with CSS, you may be aware that writing CSS code can be very repetitive. The extent to which code repeats also increases the difficulty of its maintainability. The programmer must search through many lines of code in order to upkeep its visual 'cleanliness'.

SASS was created to improve these drawbacks of writing CSS. SASS allows for nesting code, creating variables, and using for-loops; in fact, one can create and extend class-like objects - just like object oriented programming (specifically ES6) in Javascript! What once may have taken you 20 lines of code to style the third ```<p>``` tag in a nested ```<div>``` tag may only take you 10 or 15 lines of code with SASS; it may not seem like much, but what if your code base contains a few hundred lines? A few lines removed here and there might add up. In addition, the allowance for nesting of code blocks increases the readability of code blocks.

Now that I've finally got your attention, you might be wondering:

###How can I do this?

First, you'll need to make sure that you have SASS installed, which runs off Ruby Gem. If you're running iOS, this isn't a problem, as Ruby comes pre-installed on the Mac. In your terminal, simply type:
```
gem install sass
```
Verify you have correctly installed SASS by typing:
```
sass -v
```
You should see something like:
```
Sass 3.4.23 (Selective Steve)
```
If you're running on Windows, you'll first need to download and install Ruby. Check this [link](http://rubyinstaller.org/) to do just that, then follow the steps listed above.

If you have an existing project you want converted from CSS into SASS, you'll need to ```cd``` into the proper directory in your terminal and type ```sass-convert --from css --to sass -R```.

After you complete installation, you are ready to DRY up your CSS and add new awesome functionality to it!

###Just how cool is SASS, anyways?

I'm glad you asked! Let's dive right into a few of the awesome features of this preprocessing language.

1\. ***Variables***<br>
Just like in Javascript, the programmer can save values in a variable, names of which are prefixed by a `$`.
For example, we can save the color ```$almostBloodRed : $FF8000```, a width ```$theMostEvilWidth : 66.6%```, or even a font-type ```$theMostEvilFont : Slaytanic``` and pass them into the `<div>` with an id of `#divil`:
```
#divil{
    font-type: $theMostEvilFont;
    font-color: $almostBloodRed;
    width: $theMostEvilWidth;
}
```
Ok, maybe *Slaytanic* isn't really a font style, but I'm sure you understand that values saved in variables can then be passed into HTML elements.

2\. ***Nesting***<br>
Imagine having:
```
#divvy{
    a{
        //targets <a> tags nested in divvy and only divvy
    }
    p{
        //targets <p> tags nested in divvy as well
    }
}
```
instead of:
```
#divvy a{
    //same as above
}

#divvy p{
    //same as above
}
```
In this particular example, nesting the tags within the div didn't happen to save the programmer from writing noticeably fewer lines of code, although it did DRY up the code and (in my opinion) increase its readability. Imagine the possibilities on a larger code base!

Here's a better example (Thanks to [Nick](http://callmenick.com/post/an-introduction-to-sass-scss) for this one):
```
nav {
  text-align: center;
  ul {
    list-style: none;
    margin: 0;
    padding: 0;
  }
  li {
    display: inline-block;
  }
  a {
    display: block;
    padding: 5px 10px;
  }
}
```
which compiles to the following CSS:
```
nav {
  text-align: center;
}
nav ul {
  list-style: none;
  margin: 0;
  padding: 0;
}
nav li {
  display: inline-block;
}
nav a {
  display: block;
  padding: 5px 10px;
}
```
Now we're really seeing the possibilities of nesting `<div>`s within one another in our CSS files.

3\. ***Extending***<br>
Just like extending attributes from classes, we can extend properties from certain `<div>`s into others as well.
Let's say we have an element with an id of `#divil`...
```
#divil{
    width: 60px;
    font-color: blue;
    background-image: background-image: url("http://www.slayer.com/");
}
```
We can extend those attributes into one or many other elements:
```
.spawnOfThedivil{
  @extend #divil
}
```
I'm sure you can guess as to what the above code compiles:
```
.spawnOfThedivil{
  width: 60px;
  font-color: blue;
  background-image: background-image: url("http://www.slayer.com/");
}
```
Now *thats* DRYing things up, isn't it? (By the way, it's Friday the 13th, hence my evil code. Since we're on that note, time for some shameless self promotion - listen to my metal band: [Downpresser](https://www.youtube.com/watch?v=lp8c-EU6HXg&list=PLSbGOHgLB0sSI2fzSfXGBt1TYKsisQYTX))

4\. ***Mixins***<br>
"Mixins" are where SASS gets particularly object-oriented and is a great part of why SASS can be so DRYing. It's almost as though we can create a class and give it a bunch of methods, and the new instantiations of that class inherit the same values. If you're not familiar with what I'm referring to, check out this [link](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects).

For example (borrowed from the originators of [SASS](http://sass-lang.com/guide)):
```
@mixin border-radius($radius) {
  -webkit-border-radius: $radius;
     -moz-border-radius: $radius;
      -ms-border-radius: $radius;
          border-radius: $radius;
}
```
```
.box { @include border-radius(10px); }
```
equates to:
```
.box {
  -webkit-border-radius: 10px;
  -moz-border-radius: 10px;
  -ms-border-radius: 10px;
  border-radius: 10px;
}
```
The `@mixin` is called a *directive*, which seems equivalent to JS's `function` keyword. Then we give this 'function', or `@mixin` a name of `border-radius`, and we give it a bunch of "methods" that also may look familiar to the OOPer. Then we "instantiate" a `div` of class `.box` that inherits all of the `border-radius`'s properties. How cool is that?!

As you, the programmer, hopefully now can see, a ton of potential for making your CSS code cleaner, more legible, and less repetitive exists. And that's just the beginning of what SASS and SCSS can do - I've only touched upon the main topics. Other things SASS is great at includes using loops, "if" statements, and operators in your CSS code blocks! I recommend checking my references for even more ways in which you, the aspiring SASSypants, can implement your SASS in CSS.

And, by this point, if you don't see the potential for improving your CSS in many ways using SASS... then I only have one question for you:
<br>
<br>
Do you even CSS, bro?
<br>
<br>
I mean, DAMN. SASS === SIQ. I can feel it's SASSyness flowing through my veins. Can you tell? Maybe it's time for a beer...

##References:

http://sass-lang.com/guide

https://www.codecademy.com/courses/learn-sass/lessons/hello-sass/exercises/hello-sass?action=lesson_resume

http://callmenick.com/post/an-introduction-to-sass-scss

http://sass-lang.com/install

http://blog.teamtreehouse.com/how-to-choose-the-right-css-preprocessor

http://rubyinstaller.org/

http://blog.teamtreehouse.com/the-absolute-beginners-guide-to-sass

# SASS & SCSS:
##An introduction to Syntactically Awesome Style Sheets and Sassy Cascading Style Sheets

###Introduction:

SASS and SCSS, or Syntactically Awesome Style Sheets and Sassy Cascading Style Sheets, are not web page frameworks (Like Bootstrap or Materialize for HTML), and they're not libraries built on top of existing languages (like jQuery for Javascript)... So what are they?

SASS and SCSS are used somewhat interchangeably by the developer, however they have slight differences. "SASS", as the front-end developer-slash-blogger "Nick" explains, "refers to the preprocessor and syntax as a whole," while "SCSS falls under the SASS of umbrella." He continues, "[SASS] is a CSS syntax that's been turbocharged with all the goodness of SASS."

What is a preprocessor you ask? Again, we refer to our tutor Nick, who tells us that "preprocessors are tools that allow us to code CSS in a certain way, and process it into readable, pure CSS." Specifically, they compile (or, for now, are translated by the computer) from SASS into the same exact language as CSS.

Sounds pretty good to me, but...

###Why do we care?

For those of you that are familiar with CSS, you may be aware that writing CSS code can be very repetitive. The extent to which code repeats also increases the difficulty of its maintainability. The programmer must search through many lines of code in order to upkeep visual 'cleanliness' of not only the code itself, but also of the web pages which the code represents.

SASS was created to improve these drawbacks of writing CSS. SASS allows for nesting code, creating variables, and using for-loops; in fact, one can create and extend class-like objects - just like object oriented programming in Javascript! What once may have taken you 20 lines of code in order to style the third ```<p>``` tag in a nested ```<div>``` tag may only take you 10 or 15 lines of code; it may not seem like much, but what if your code base contains hundreds of lines? A few lines removed here and there might add up. In addition, the allowance for nesting of code blocks increases the readability of the code base. Imagine having:

```
div{
    a{
        //targets <a> tags nested in div with styling here
    }
    p{
        //targets <p> tags nested in same div with more styling
    }
}

```

instead of:

```
div a{
    //same as above
}

div p{
    //same as above
}
```

In this particular example, nesting the tags within the div didn't happen to save the programmer from writing noticeably fewer lines of code, although it did DRY up the code and (in my opinion) increase its readability. Imagine the possibilities on a larger code base!

Now that I've finally got your attention, you might be wondering:

###How can I do this?

First, you'll need to make sure that you have SASS installed, which runs off Ruby Gem (which I'm not familiar with myself). If you're running iOS, this isn't a problem, as Ruby comes pre-installed on the Mac. In your terminal, simply type:

```
gem install sass
```

Ensure you have SASS installed by then typing:

```
sass -v
```

You should see something like:

```
Sass 3.4.23 (Selective Steve)
```

If you're running on Windows, you'll first need to download and install Ruby. Check this [link](http://rubyinstaller.org/) to do just that, then follow the steps listed above.

***After you complete installation, you are ready to DRY up your CSS and add new awesome functionality to it!***

<!-- Part 2 (Often answers “how can I do this?”)
Part 3 (Often expands on how cool this is.)
Conclusion -->

##References:

http://sass-lang.com/guide

https://www.codecademy.com/courses/learn-sass/lessons/hello-sass/exercises/hello-sass?action=lesson_resume

http://callmenick.com/post/an-introduction-to-sass-scss

http://sass-lang.com/install

http://blog.teamtreehouse.com/how-to-choose-the-right-css-preprocessor

http://rubyinstaller.org/

---
layout: post
title:      "Arrow Function"
date:       2019-06-09 10:48:32 -0400
permalink:  arrow_function
---

### ONE SATURDAY MORNING WITH KYLE SIMSON – THE AUTHOR OF “YOU DO NOT KNOW JS: ES6 & BEYOND”

![](https://live.staticflickr.com/65535/48030459728_ca0428e9bf_z.jpg)

4 am on a Saturday morning. Just a perfect time to snuggle on a couch with a cup of coffee and a laptop surrounded by snoring cats and a soundly breathing retriever. It’s a perfect moment of serenity and integrity with self to appreciate the times we are living in when the best of geniuses are just a click away to enjoy their presence and a guiding touch. Just one light click with a finger will open up the universe to dive in and dissolve in a pure intellectual pleasure of sharp and daring ideas that challenge the trends and uncover the group thinkers. 

Yes, I totally caught myself being a groupthinker brainwashilly agreeing with the whole world that ES6 arrow functions are nice and elegant new advance to love and completely replace the old fashioned functions.  Even though the bells in my brain were constantly ringing in a great cacophony signaling something odd at almost every attempt to use an arrow function, I was so blind and sure that that one I must adore and never question it’s universe beauty. What a foolish groupthinker I was… until that one light magic click that started the video of the “ES6: The Right Parts” course with Kyle Simpson.

“I’m going to take you through the tour of the staff I do not think you should pay attention to. But by popular demand I have to start by going into a feature that I really do not think you should pay attention to. I wouldn’t really call it the right part in the sense that this is the place to start. It’s not objectively bad and it doesn’t not have a zero value in it, but that’s the place where everyone’s journey with ES6 seems to start. I’d be remised if I did not start your journey with an arrow function. ” he started and that made me to hold my breath away and begin greedily absorb every single word I heard. That type of ideas magnetizes me, glues me on  and makes me vigorously uncover the hidden parts of the puzzle I never knew they even exist. What a brilliant mind! He puts his expertise into the analytical view of the code from a readability prospective. Why? Because the real global productivity of the average programmer is only 5 lines of code per day! Five lines! Per whole day! The rest of the time we spend reading the code, which is by that means is intended for us, people, to read. Even machines execute that code less in total hours than we read it. What a discovery! The programming code is for communicating with humans! We are being paid mostly for the ability to read that code, not for publishing our own novels in scripts.  

That means if we are looking to improve and advance the coding language, it should go the way of increasing the readability. Otherwise 70% of our time would end up to become a great misery. So,  does the arrow function really gives us that benefit of being increasingly  readable  - not just a fashion beauty model? Apparently, the answer is no. It gives us confusions, headaches, erroneous functionality and does not even save us much time to type it in.  Ah-oh, looks like we are falling out of the trend here… Out of the trend of hieroglyphic who-knows-what-they-mean code producers toward the trend of those with in-depth knowledge and real understanding of what they are doing informed masters! So, off we go!

It’s time to ask that one question: “Why exactly the arrow functions are a bad choice for most of the cases?” Here is the whole list of arguments in that favor to read before stepping out of that “so-common” trend. 



1. Variations in syntax is a detractor from an overall value
*              `()=>3` – if number of arguments is 0, >1, spread, non-traditional  arguments are in parenthesis                  
*              `x=>3` – 1 argument is not in parenthesis
*              `(…x) => 3` – visual hiccup? Is there a function invocation?
*              `(x,y) => 3`
*              `var foo = => 3` – does not confuse you? at all??? 
*              ` _=>3`
*              ` 	=>3`
*              `x=>({a:b})` – object is in parenthesis
         
2. Statement and expression confusion. Statements are not valid for a concise form
*          `x => { try {3} catch(e) {} }` – statement, not expression – not going to work
*          `if.. else` - statement
*          `for, while` - statements 
3.	Implying return confusion ( not consistent)
*          `x=>3` <- implied
*          `x=>{return 3}` <- not implied
4.	Syntactical anonymousness
*          can’t self-reference (recursion, event handler that needs to unbind itself)
*          non-visible in a stack traces, so are non-debuggable
*          name inferencing does not work for functions as argument of other functions which are 99.999% of all arrow functions are  
5.	Promises 
*          hard to debug due to  anonymousness when exception thrown
6.	Decision flow chart. Is this the one you really want to run through every time you make a decision if to write an arrow function? The word “function” is definitely could be typed faster then going though all these steps.

 ![](https://live.staticflickr.com/65535/48030533587_f5e27bf8a1_z.jpg)
 [Decision Flowchart](https://likeahouseafire.com/2017/02/20/how-pronounce-fat-arrow/)


There is one specific case, however, when arrow functions are actually very useful: when you need to invoke a function inside a function that is a parameter of an object itself than going one level up in the scope with “this” really helps.

```
var obj= {
     id:42;
     foo: function foo(){
	   setTimeOut(()=>{
              console.log(this.id) <- points to the right scope the extract the id from obj
       },100)
    }
}
```
That one case was most likely what the arrow functions were created for. And just because they are so damn cute people start welcoming them to all random parties that are related to use of functions.

*With all said above I am now a proud endorser of the idea of a critical thinking and trusting one’s intuition. Is the new YYY really the old XXX? May be the new YYY was just conveniently created to complement the old XXX and shine where the XXX really straggles, but not completely replace where the XXX has excelled for years and can perfectly do so for many more to come. *


***Epilogue***

 At 6 am my cup is empty, my cats are gone, the room is all stuffed with a bright sunlight, and the whole world of ES6 is flipped upside down. And it will never be the same…   


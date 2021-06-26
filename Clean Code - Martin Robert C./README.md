# Clean Code by Martin Robert C.
Summarized by Thiramate A.

## Intro

You're reading this book for two reasons. First, you are a programmer. Second, you want to be a **better** programmer. We are going to look at code from every different direction. We'll be able to tell the difference between good code and bad code. We’ll know how to write good code. And we’ll know how to transform bad code into good code.

## Chapter 1 - Clean Code

### Bad Code

There was a company, in the late 80s, wrote a _killer_ app. It was very popular and used by lots of professionals. Time fly, load times grew up and crashes increased. Bugs were not repaired from one release to the next. This happended because they had rushed the product to market and had made a huge mess in the code. They keep added more and more features, the code get worse and worse until they cannot manage it any longer. _It was the bad code that brought the company down._

Why did you write bad code? Maybe because you are in rush or trying to go fast. Perhaps you felt you didn't have time to do a good job as your boss would be angry with you if you delay the delivery because you clean up your code. Perhaps you were so tired of working on this program and wanted it to be over. Or even you looked at the backlog and saw a lot of stuff that you had promised to get them done so you need to bang this task fast so you can move on to the next.

We have all felt to seeing messy and inefficient program work and thinking that working mess is better than nothing. We have all said that we will go back and clean it up later. Oh yes, we never know when.

### The Total Cost of Owning a Mess

If you have been working as a programmer for longer than a few years, you have probably been slowed down by messy code. Every change you make always breaks some part of the code. Then you need to twist in order to add something new or modify existing code. By doing that knots can be added. Overtime the mess becomes bigger and deeper until no way to clean it up.

The more mess builds the less team productivity. As productivity decrease, management can do only thing which adds more staff to the project and hopes the productivity will be increased. That not gonna help much as new staffs need time to understand the design of the system. Maybe they need the explanation from existing staffs while they are under horrific pressure to increase productivity. So they all make more and more messes.

### What is Clean Code?

> I like my code to be elegant and efficient. The logic should be straightforward to make it hard for bugs to hide, the dependencies minimal to ease maintenance, error handling complete according to an articulated strategy, and performance close to optimal so as not to tempt people to make the code messy with unprincipled optimizations. Clean code does one thing well — Bjarne Stroustrup, inventor of C++

`Elegant` in this case mean pleasing. Apparently, Bjarne think that clean codeis **pleasing** to read. He also mentions that `error handling should be complete`. This goes to the discipline of paying attention to details. Error handling is just one way for programmer to seeks the details. Furthermore, `clean code does one thing well`, this mean each function, each class, each module exposes a single-minded attitude that remains entirely undistracted, and unpolluted, by the surrounding details.<br/><br/>

> Clean code is simple and direct. Clean code reads like well-written prose. Clean code never obscures the designer’s intent but rather is full of crisp abstractions and straightforward lines of control — Grady Booch, Author of Object Oriented Analysis and Design with Applications

Grady makes some of the same points as Bjarne, but he takes a readability perspective. He's using word `crisp abstraction`, our code should be matter-of-fact. It should contain only what is necessary.<br/><br/>

> Clean code can be read, and enhanced by a developer other than its original author. It has unit and acceptance tests. It has meaningful names. It provides one way rather than many ways for doing one thing. It has minimal dependencies, which are explicitly defined, and provides a clear and minimal API. Code should be literate since depending on the language, not all necessary information can be expressed clearly in code alone — “Big” Dave Thomas, founder of OTI, godfather of the Eclipse strategy

Dave thinks that clean code makes it easy for other people to enhance it. Code, without tests, is not clean. No matter how elegant it is, no matter how readable and accessible.<br/><br/>

> I could list all of the qualities that I notice in clean code, but there is one overarching quality that leads to all of them. Clean code always looks like it was written by someone who cares. There is nothing obvious that you can do to make it better. All of those things were thought about by the code’s author, and if you try to imagine improvements, you’re led back to where you are, sitting in appreciation of the code someone left for you. Code left by someone who cares deeply about the craft — Michael Feathers, author of Working Effectively with Legacy Code

Michael hit it on the head. Clean code is code that has been taken care of. Someone has taken the time to keep it simple and orderly. They have paid appropriate attention to details.


# Clean Code by Martin Robert C.
Summarized by Thiramate A.

## Chapter 1 - Clean Code

You are reading this book for two reasons. First, you are a **programmer**. Second, you want to be a **better** programmer.

### There Will Be Code

- We never get rid of code because code represents details of the requirements.
- Remember that code is really the language in which we ultimately express the requirements.

### Bad Code

#### Case Study

The company wrote the popular app and was used by a lot of professionals but the company went out of business a short time after release. The reasons are
- They are in rush and made a huge mess in the code
- The more features are added, the code gets worse

In conclusion, bad code can bring down the company

#### Why did you write bad code?

- You are trying to go fast and ignore the code quality
- You are tired and want it to be over
- You feel better to see the messy application running than nothing

### The Total Cost of Owning a Mess

- Productivity has been slowed down by a messy code
- Over time the mess becomes so big and so deep and so tall, there is no way to clean up at all

#### The Grand Redesign in the Sky

Spending time keeping your code clean is not just cost effective, it’s a matter of professional survival.

#### Attitude

- The managers and marketers look to us for the information to make promises and commitments
- The users look to us to validate the way the requirements will fit into the system
- The project managers look to us to help work out the schedule
- It is unprofessional for the programmers to write the code to align with the will of the managers who don't understand the risks of making messes

#### The Primal Conundrum

- You will not make the deadline by making the mess
- The only way to go fast is to keep the code as clean as possible all the time

#### The Art of Clean Code?

- Writing clean code is a lot like painting a picture
- Writing clean code requires discipline
- A programmer with **code-sense** will look at a messy code and see options and variations

### What is Clean Code?

#### Bjarne Stroustrup, inventor of C++ and author of The C++ Programming Language

- Code should be elegant (pleasing to read) and efficient
- The logic should be straightforward
- Error handling should be complete (paying attention to details)
- Does one thing well

#### Grady Booch, author of Object Oriented Analysis and Design with Applications

- Simple and direct
- Read like well-written prose
- Should contain only what is necessary

#### “Big” Dave Thomas, founder of OTI, godfather of the Eclipse strategy

- Can be read and enhanced by another developer
- Has unit and acceptance tests
- Has meaningful name
- Does one thing well
- Has minimal dependencies
- Provide clear and minimal API

#### Michael Feathers, author of Working Effectively with Legacy Code

- Always looks like it was written by someone who cares
- Clean code is code that has been taken care of

#### Clean code is code that has been taken care of.

- Contains no duplication
- Expresses all the design ideas that are in the system such as meaningful name
- Minimizes the number of entities such as classes, methods and functions
- Building of simple abstraction

#### Ward Cunningham, inventor of Wiki, inventor of Fit, coinventor of eXtreme Programming. Motive force behind Design Patterns. Smalltalk and OO thought leader. The godfather of all those who care about code.

- When reading clean code, it turns out to be pretty much what you expected. It will be obvious, simple and compelling
- Beautiful code makes the language look like it was made for the problem
- It is the programmer responsibility to make the language look simple

#### We Are Authors

- Ratio of time spent reading vs writing should be over 10:1
- We are constantly reading old code as part of the effort to write new code

#### The Boy Scout Rule

- The code has to be kept clean over time
- Leave the campground cleaner than you found it

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
- They are in rush and made a huge mess in the code.
- The more features are added, the code gets worse.

In conclusion, bad code can bring down the company

#### Why did you write bad code?

- You are trying to go fast and ignore the code quality.
- You are tired and want it to be over.
- You feel better to see the messy application running than nothing.

### The Total Cost of Owning a Mess

- Productivity has been slowed down by a messy code.
- Over time the mess becomes so big and so deep and so tall, there is no way to clean up at all.

#### The Grand Redesign in the Sky

Spending time keeping your code clean is not just cost effective, it’s a matter of professional survival.

#### Attitude

- The managers and marketers look to us for the information to make promises and commitments.
- The users look to us to validate the way the requirements will fit into the system.
- The project managers look to us to help work out the schedule.
- It is unprofessional for the programmers to write the code to align with the will of the managers who don't understand the risks of making messes.

#### The Primal Conundrum

- You will not make the deadline by making the mess.
- The only way to go fast is to keep the code as clean as possible all the time.

#### The Art of Clean Code?

- Writing clean code is a lot like painting a picture.
- Writing clean code requires discipline.
- A programmer with **code-sense** will look at a messy code and see options and variations.

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

## Chapter 2 - Meaningful Names

### Use Intention-Revealing Names

Variable name should tell you why it exists, what it does and how it is used. With a simple name, it is easy to understand what's going on.
```java
// Bad
int d; // elapsed time in days

// Good
int elapsedTimeInDays;
int daysSinceCreation;
int fileAgeInDays
```

### Avoid Disinformation

- Programmers must avoid leaving false clues that obscure the meaning of code. For example, `hp`, `aix` and `sco` because they are the names of Unix platforms or variants.
- Don't use `accountList` refer the group of accounts unless it is actually a `List`. The word list means something specific to programmers. Use `accountGroup` or just plain `accounts` would be better.
- Beware of using names which vary in small ways such as `XYZControllerForEfficientHandlingOfStrings` and `XYZControllerForEfficientStorageOfStrings`. It is difficult to spot the difference.
- A truly awsful example of disinformative name would be lowercase `L` or uppercase `O` because they look almost entirely like the constants one and zero, respectively.

### Make Meaningful Distinctions

### Use Pronounceable Names

Name should be pronounceable. If you can’t pronounce it, you can’t discuss it without sounding like an idiot.

### Use Searchable Names

- Single-letter names can ONLY be used as local variables inside short methods.
- The length of a name should correspond to the size of its scope.
- Give a search friendly name for variable that might be seen or used in multiple places.

### Avoid Encodings

Encoded names are seldom pronounceable and are easy to mis-type.

### Avoid Mental Mapping

- Readers shouldn’t have to mentally translate your names into other names they already know.
- Professional programmers use their powers for good and write code that others can understand.

### Class Names

- Classes and objects should have noun or noun phrase names like `Customer`, `WikiPage`, `Account`, and `AddressParser`.
- Avoid words like `Manager`, `Processor`, `Data`, or `Info` in the name of a class. A class name should not be a verb.

### Method Names

- Methods should have verb or verb phrase names like `postPayment`, `deletePage`, or `save`.
- Accessors, mutators, and predicates should be named for their value and prefixed with `get`, `set`, and `is`.

### Don't be Cute

- Never use name like `HolyHandGrenade`, it's cute but `DeleteItems` is definitely better name in this case.
- Choose clarity over entertainment value.

### Pick One Word per Concept

- Pick one word for one abstract concept and stick with it. For example, it’s confusing to have `fetch`, `retrieve`, and `get` as equivalent methods of different classes.
- A consistent lexicon is a great benefit to the programmers who must use your code.

### Don't Pun

Let’s say we have many classes where `add` will create a new value by adding or concatenating two existing values. Now let’s say we are writing a new class that has a method that puts its single parameter into a collection. We should use a name like `insert` or `append` instead of `add` in this case. To call the new method `add` would be a pun.

### Use Solution Domain Names

Remember that the people who read your code will be programmers. So go ahead and use computer science (CS) terms, algorithm names, pattern names, math terms, and so forth. It is not wise to draw every name from the problem domain because we don’t want our coworkers to have to run back and forth to the customer asking what every name means when they already know the concept by a different name.

### Use Problem Domain Names

When there is no `programmer-eese` for what you’re doing, use the name from the problem domain. At least the programmer who maintains your code can ask a domain expert what it means.

### Add Meaningful Context

- You need to place names in context for your reader by enclosing them in well-named classes, functions, or namespaces.
- You can add context by using prefixes: `addrFirstName`, `addrLastName`, `addrState`, and so on. 

### Don’t Add Gratuitous Context

Shorter names are generally better than longer ones, so long as they are clear. Add no more context to a name than is necessary.

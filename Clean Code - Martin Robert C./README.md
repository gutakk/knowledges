# Clean Code by Martin C. Robert
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

## Chapter 3 - Functions

### Small!

- Functions should be small.
- They should have no more than 4 lines of code.

### Do One Thing

Funtions should do one thing. They should do it well. They should do it only.

### One Level of Abstraction per Function

In order to make sure our functions are doing `one thing`, we need to make sure that the statements within our function are all at the same level of abstraction.

### Reading Code from Top to Bottom: The Stepdown Rule

We want to be able to read the program as though it were a set of TO paragraphs, each of which is describing the current level of abstraction and referencing subsequent TO paragraphs at the next level down. 

```
To include the setups and teardowns, we include setups, then we include the test page content, and then we include the teardowns.

To include the setups, we include the suite setup if this is a suite, then we include the regular setup.

To include the suite setup, we search the parent hierarchy for the “SuiteSetUp” page and add an include statement with the path of that page. To search the parent…
```

### Use Descriptive Names

- Don’t be afraid to make a name long. A long descriptive name is better than a short mysterious name.
- Don’t be afraid to spend time choosing a name.
- Be consistent in your names. Use the same phrases, nouns, and verbs in the function names you choose for your modules.

### Function Arguments

- The ideal number of arguments for a function is zero.
- More than 2 arguments should be avoided where possible.
- When a function seems to need more than two or three arguments, it is likely that some of those arguments ought to be wrapped into a class of their own.
  ```java
  Circle makeCircle(double x, double y, double radius);
  Circle makeCircle(Point center, double radius);
  ```
- Flag arguments are ugly. Passing a boolean into a function is a truly terrible practice. It loudly proclaiming that this function does more than one thing. It does one thing if the flag is true and another if the flag is false!

### Have No Side Effects

Side effects are lies. Your function promises to do one thing, but it also does other hidden things. Sometimes it will make unexpected changes to the variables of its own class.

### Command Query Separation

Functions should either do something or answer something, but not both. Either your function should change the state of an object, or it should return some information about that object. Doing both often leads to confusion.

### Prefer Exceptions to Returning Error Codes

- Returning error codes from command functions is a subtle violation of command query separation.
- If you use exceptions instead of returned error codes, then the error processing code can be separated from the happy path code and can be simplified.
- Try/catch blocks are ugly in their own right. They confuse the structure of the code and mix error processing with normal processing. So it is better to extract the bodies of the try and catch blocks out into functions of their own.

### Don't Repeat Yourself (DRY)

- Duplication may be the root of all evil in software.
- Duplication is a problem because it bloats the code and will require more than one modification should the algorithm ever have to change. It is also a more than one opportunity for an error of omission.

### Structured Programming

There should only be one `return` statement in a function, no `break` or `continue` statements in a loop, and never ever any `goto` statements.

## Chapter 4 - Comments

The proper use of comments is to compensate for our failure to express ourself in code. So when you find yourself in a position where you need to write a comment, think it through and see whether there isn’t some way to turn the tables and express yourself in code.

### Comments Do Not Make Up for Bad Code

Clear and expressive code with few comments is far superior to cluttered and complex code with lots of comments.

### Explain Yourself in Code

It takes only a few seconds of thought to explain most of your intent in code. In many cases it’s simply a matter of creating a function that says the same thing as the comment you want to write.

```java
// Bad
// Check to see if the employee is eligible for full benefits
   if ((employee.flags & HOURLY_FLAG) &&
       (employee.age > 65))

// Good
if (employee.isEligibleForFullBenefits())
```

### Good Comments

#### Legal Comments

Sometimes our corporate coding standards force us to write certain comments for legal reasons. For example, copyright and authorship statements are necessary and reasonable things to put into a comment at the start of each source file.

#### Informative Comments

It is sometimes useful to provide basic information with a comment. For example, comment that explains the return value of an abstract method
```java
// format matched kk:mm:ss EEE, MMM dd, yyyy
Pattern timeMatcher = Pattern.compile(“\\d*:\\d*:\\d* \\w*, \\w* \\d*, \\d*”);
```

#### Explanation of Intent

Sometimes a comment goes beyond just useful information about the implementation and provides the intent behind a decision.

#### Clarification

Sometimes it is just helpful to translate the meaning of some obscure argument or return value into something that’s readable. When its part of the standard library, or in code that you cannot alter, then a helpful clarifying comment can be useful.

#### Warning of Consequences

Sometimes it is useful to warn other programmers about certain consequences. For example, a comment that explains why a particular test case is turned off.

#### TODO Comments

It is sometimes reasonable to leave `To do` notes in the form of `//TODO` comments. In the following case, the TODO comment explains why the function has a degenerate implementation and what that function’s future should be.

#### Amplification

A comment may be used to amplify the importance of something that may otherwise seem inconsequential.

### Bad Comments

#### Mumbling

Plopping in a comment just because you feel you should or because the process requires it is a hack. If you decide to write a comment, then spend the time to make sure it is the best comment you can write.

#### Redundant Comments

Avoid the comment that not more informative than the code. The comment probably takes longer to read than the code itself.

#### Misleading Comments

Sometimes, with all the best intentions, a programmer makes a statement in his comments that isn’t precise enough to be accurate.

#### Mandated Comments

It is just plain silly to have a rule that says that every function must have a javadoc, or every variable must have a comment. Comments like this just clutter up the code, propagate lies, and lend to general confusion and disorganization.

#### Journal Comments

Long ago we didn’t have source code control systems that did log of every change that has ever been made for us. Nowadays, however, these long journals are just more clutter to obfuscate the module. They should be completely removed.

#### Noise Comments

Sometimes you see comments that are nothing but noise. They restate the obvious and provide no new information.
```java
/** The day of the month. */
private int dayOfMonth;
```

#### Don’t Use a Comment When You Can Use a Function or a Variable

```java
// Bad
// does the module from the global list <mod> depend on the
// subsystem we are part of?
if (smodule.getDependSubsystems().contains(subSysMod.getSubSystem()))

// Good
ArrayList moduleDependees = smodule.getDependSubsystems();
String ourSubSystem = subSysMod.getSubSystem();
if (moduleDependees.contains(ourSubSystem))
```

#### Position Markers

Sometimes programmers like to mark a particular position in a source file. For example
```java
// Actions //////////////////////////////////
```

#### Closing Brace Comments

This might make sense for long functions with deeply nested structures but if you find yourself wanting to mark your closing braces, try to shorten your functions instead.
```java
// Bad
try {
  while {
    ...
  } // while
  ...
} // try
```

#### Attributions and Bylines

```java
/* Added by Thiramate A */
```
Source code control systems are very good at remembering who added what, when. There is no need to pollute the code with little bylines.

#### Commented-Out Code

Some practices are as odious as commenting-out code. Don’t do this!

#### HTML Comments

HTML in source code comments is an abomination. It makes the comments hard to read in the one place where they should be easy to read.

#### Nonlocal Information

If you must write a comment, then make sure it describes the code it appears near. Don’t offer systemwide information in the context of a local comment.

#### Too Much Information

Don’t put interesting historical discussions or irrelevant descriptions of details into your comments.

#### Inobvious Connection

The connection between a comment and the code it describes should be obvious. If you are going to the trouble to write a comment, then at least you’d like the reader to be able to look at the comment and the code and understand what the comment is talking about.

#### Function Headers

Short functions don’t need much description. A well-chosen name for a small function that does one thing is usually better than a comment header.

## Chapter 5 - Formatting

### Vertical Formatting

- Small files are usually easier to understand than large files are.
- We would like a source file to be like a newspaper article. The topmost parts of the source file should provide the high-level concepts and algorithms. Detail should increase as we move downward, until at the end we find the lowest level functions and details in the source file.
- Each line represents an expression or a clause, and each group of lines represents a complete thought. Those thoughts should be separated from each other with blank lines.
- Concepts that are closely related should be kept vertically close to each other and belong in the same source file.
- Variables should be declared as close to their usage as possible.
- Instance variables should be declared at the top of the class.
- Dependent Functions. If one function calls another, they should be vertically close, and the caller should be above the callee.

### Horizontal Formatting

- Lines should not be longer than 120 characters.
- Use horizontal white space to associate things that are strongly related and disassociate things that are more weakly related.
- Indent the lines of source code in proportion to their position in the hiearchy.

### Team Rules

A team of developers should agree upon a single formatting style, and then every member of that team should use that style.

## Chapter 6 - Objects and Data Structures

### Data Abstraction

Hiding implementation is not just a matter of putting a layer of functions between the variables. Hiding implementation is about abstractions! A class does not simply push its variables out through getters and setters. Rather it exposes abstract interfaces that allow its users to manipulate the `essence` of the data, without having to know its implementation.

### Data/Object Anti-Symmetry

- Objects hide their data behind abstractions and expose functions that operate on that data. Data structure expose their data and have no meaningful functions.
- Procedural code (code using data structures) makes it easy to add new functions without changing the existing data structures.
- OO code, on the other hand, makes it easy to add new classes without changing existing functions.

### The Law of Demeter

- Module should not know about the innards of the objects it manipulates.
- The Law of Demeter says that a method `f` of a class `C` should only call the methods of these
  - C
  - An object created by `f`
  - An object passed as an argument to `f`
  - An object held in an instance variable of `C`

## Chapter 7 - Error Handling

### Use Exceptions Rather Than Return Code

It is better to throw an exception when you encounter an error. The calling code is cleaner. Its logic is not obscured by error handling.

### Write Your Try-Catch-Finally Statement First

Try blocks are like transactions. Your catch has to leave your program in a consistent state, no matter what happens in the try. For this reason it is good practice to start with a try-catch-finally statement when you are writing code that could throw exceptions. This helps you define what the user of that code should expect, no matter what goes wrong with the code that is executed in the try.

### Use Unchecked Exceptions

Checked exceptions can sometimes be useful if you are writing a critical library: You must catch them. But in general application development the dependency costs outweigh the benefits.

### Provide Context with Exceptions

- Each exception that you throw should provide enough context to determine the source and location of an error.
- Create informative error messages and pass them along with your exceptions. Mention the operation that failed and the type of failure.
- If you are logging in your application, pass along enough information to be able to log the error in your catch.

### Define Exception Classes in Terms of a Caller’s Needs

- Wrapping third-party APIs is a best practice. When you wrap a third-party API, you minimize your dependencies upon it.
- Wrapping also makes it easier to mock out third-party calls when you are testing your own code.

### Define the Normal Flow

- You wrap external APIs so that you can throw your own exceptions, and you define a handler above your code so that you can deal with any aborted computation.

```java
// Bad
try {
  MealExpenses expenses = expenseReportDAO.getMeals(employee.getID());
  m_total += expenses.getTotal();
} catch(MealExpensesNotFound e) {
  m_total += getMealPerDiem();
}

// Good
MealExpenses expenses = expenseReportDAO.getMeals(employee.getID());
m_total += expenses.getTotal();
```

### Don't Return Null

- When we return null, we are essentially creating work for ourselves and foisting problems upon our callers. All it takes is one missing null check to send an application spinning out of control.
- If you are tempted to return null from a method, consider throwing an exception or returning a SPECIAL CASE object instead.
- If you are calling a null-returning method from a third-party API, consider wrapping that method with a method that either throws an exception or returns a special case object.

### Don't Pass Null

Returning null from methods is bad, but passing null into methods is worse. Unless you are working with an API which expects you to pass null, you should avoid passing null in your code whenever possible.

## Chapter 8 - Boundaries

### Using Third-Party Code

- There is a natural tension between the provider of an interface and the user of an interface. Providers of third-party packages and frameworks strive for broad applicability so they can work in many environments and appeal to a wide audience.
- audience. Users, on the other hand, want an interface that is focused on their particular needs. This tension can cause problems at the boundaries of our systems.

```java
// Non generic
Map sensors = new HashMap();
Sensor s = (Sensor)sensors.get(sensorId);

// Generic
Map<Sensor> sensors = new HashMap<Sensor>();
Sensor s = sensors.get(sensorId);

// Cleaner
public class Sensors {
  private Map sensors = new HashMap();
  public Sensor getById(String id) {
    return (Sensor) sensors.get(id);
  }
  //snip
}
```

### Exploring and Learning Boundaries

- It’s not our job to test the third-party code, but it may be in our best interest to write tests for the third-party code we use.
- Instead of experimenting and trying out the new stuff in our production code, we could write some tests to explore our understanding of the third-party code.

### Learning Tests Are Better Than Free

- The learning tests were precise experiments that helped increase our understanding.
- Learning tests verify that the third-party packages we are using work the way we expect them to.

### Clean Boundaries

- Code at the boundaries needs clear separation and tests that define expectations.
- We should avoid letting too much of our code know about the third-party particulars.
- It’s better to depend on something you control than on something you don’t control.

## Chapter 9 - Unit Tests

### The Three Laws of TDD

- **First Law**: You may not write production code until you have written a failing unit test.
- **Second Law**: You may not write more of a unit test than is sufficient to fail, and not compiling is failing.
- **Third Law**: You may not write more production code than is sufficient to pass the currently failing test.

### Keeping Tests Clean

- Test code is just as important as production code.
- It requires thought, design, and care.
- It must be kept as clean as production code.

#### Tests Enable the -ilities

- If you don’t keep your tests clean, you will lose them.
- Unit tests that keep our code flexible, maintainable, and reusable.
- If you have tests, you do not fear making changes to the code!
- If your tests are dirty, then your ability to change your code is hampered.

### Clean Tests

- What makes a clean test? Three things. Readability, readability, and readability. Readability is perhaps even more important in unit tests than it is in production code.
- What makes tests readable? clarity, simplicity, and density of expression. In a test you want to say a lot with as few expressions as possible.
```java
public void testGetPageHieratchyAsXml() throws Exception {
  crawler.addPage(root, PathParser.parse(“PageOne”));
  crawler.addPage(root, PathParser.parse(“PageOne.ChildOne”));
  crawler.addPage(root, PathParser.parse(“PageTwo”));
  
  request.setResource(“root”);
  request.addInput(“type”, “pages”);
  Responder responder = new SerializedPageResponder();
  SimpleResponse response = (SimpleResponse) responder.makeResponse(new FitNesseContext(root), request);
  String xml = response.getContent();
  
  assertEquals(“text/xml”, response.getContentType());
  assertSubString(“<name>PageOne</name>”, xml);
  assertSubString(“<name>PageTwo</name>”, xml);
  assertSubString(“<name>ChildOne</name>”, xml);
}

// Refactored
public void testGetPageHierarchyAsXml() throws Exception {
  makePages(“PageOne”, “PageOne.ChildOne”, “PageTwo”);
  
  submitRequest(“root”, “type:pages”);
  
  assertResponseIsXML();
  assertResponseContains(
    “<name>PageOne</name>”, “<name>PageTwo</name>”, “<name>ChildOne</name>”
  );
}
```

### Domain-Specific Testing Language

Rather than using the APIs that programmers use to manipulate the system, we build up a set of functions and utilities that make use of those APIs and that make the tests more convenient to write and easier to read. These functions and utilities become a specialized API used by the tests.

### One Assert Per Test

- Tests come to a single conclusion that is quick and easy to understand.
- Best thing we can say is that the number of asserts in a test ought to be minimized.
- Perhaps a better rule is that we want to test a single concept in each test function. We don’t want long test functions that go testing one miscellaneous thing after another.

### F.I.R.S.T

- **Fast**: Tests should be fast so you can run them frequently.
- **Independent**: Tests should not depend on each other. One test should not set up the conditions for the next test.
- **Repeatable**: Tests should be repeatable in any environment even on your laptop without network.
- **Self-Validating**: Tests should have a boolean output.
- **Timely**: Unit tests should be written just before the production code that makes them pass.

## Chapter 10 - Classes

### Class Organization

- Following the standard Java convention, class should begin with list of variables.
  1. Public static constants
  2. Private static variables
  3. Private instance variables
- Then follow by the functions
  1. Public functions
  2. Private functions

#### Encapsulation

Variables and utility functions should be private but we can make them protected sometimes so that they can be accessed by a test from the same package.

### Classes Should Be Small!

- Count **responsibilities**
- The more ambiguous the class name, the more likely it has too many responsibilities. For example `Processor` or `Manager`.
- We should write a brief description of the class in about 25 words, without using the words `if`, `and` `or` or `but`.

#### The Single Responsibility Principle

- Class or module should have one and only `reason to change`.
- System with many small classes are better than a system with a few large classes. For example, do you want your tools organized into toolboxes with many small drawers but containing well-defined and well-labeled components or few drawers that you just toss everything into?

#### Cohesion

- The more variables a method manipulates the more cohesive that method is to its class.
- When cohesion is high, the methods and variables of the class are co-dependent and hang together as a logical whole.

#### Maintaining Cohesion Results in Many Small Classes

- When classes lose cohesion, split them!
- Breaking a large function into many smaller functions often gives us the opportunity to split several smaller classes out as well.

### Organizing for Change

- We should not modify classes, extend them instead to reduce the risk of breaking other code in the class.
- We want to structure our systems so that we muck with as little as possible when we update them with new or changed features.

#### Isolating from Change

Classes should depend on abstractions, not concrete details.

## Chapter 11 - Systems

### Separate Constructing a System from Using It

Software systems should separate the startup process, when the application objects are constructed and the dependencies are “wired” together, from the runtime logic that takes over after startup. For example

```java
public Service getService() {
  if (service == null)
    service = new MyServiceImpl(…); // Good enough default for most cases?
  return service;
}
```

This is the **LAZY INITIALIZATION/EVALUATION** idiom, and it has several merits. We don’t get the overhead of construction unless we actually use the object, and our startup times can be faster as a result. We also ensure that null is never returned. However, we now have a hard-coded dependency on `MyServiceImpl` and everything its constructor requires. We can’t compile without resolving these dependencies, even if we never actually use an object of this type at runtime!

#### Separation of Main

One way to separate construction from use is simply to move all aspects of construction to main, or modules called by main.

#### Dependency Injection

- In the context of dependency management, an object should not take responsibility for instantiating dependencies itself. 
- Instead, it should pass this responsibility to another “authoritative” mechanism, thereby inverting the control.

### Scaling Up

- We should implement only today’s stories, then refactor and expand the system to implement new stories tomorrow. This is the essence of iterative and incremental agility.
- Test-driven development, refactoring, and the clean code they produce make this work at the code level.
- Software systems are unique compared to physical systems. Their architectures can grow incrementally, if we maintain the proper separation of concerns.

### Test Drive the System Architecture

An optimal system architecture consists of modularized domains of concern, each of which is implemented with Plain Old Java (or other) Objects. The different domains are integrated together with minimally invasive Aspects or Aspect-like tools. This architecture can be test-driven, just like the code.

### Optimize Decision Making

- Modularity and separation of concerns make decentralized management and decision making possible.
- It isn’t lazy or irresponsible to postpone decisions until the last possible moment. It lets us make informed choices with the best possible information. A premature decision is a decision made with suboptimal knowledge.

### Use Standards Wisely, When They Add Demonstrable Value

- Standards make it easier to reuse ideas and components, recruit people with relevant experience, encapsulate good ideas, and wire components together.
- However, the process of creating standards can sometimes take too long for industry to wait, and some standards lose touch with the real needs of the adopters they are intended to serve.

### Systems Need Domain-Specific Languages

- A good DSL minimizes the `communication gap` between a domain concept and the code that implements it, just as agile practices optimize the communications within a team and with the project’s stakeholders.
- DSLs, when used effectively, raise the abstraction level above code idioms and design patterns. They allow the developer to reveal the intent of the code at the appropriate level of abstraction.

## Chapter 12 - Emergence

### Getting Clean via Emergent Design

According to Kent Beck, a design is "simple" if it follows these rules (The rules are given in order of importance):
- Runs all the tests.
- Contains no duplication.
- Expresses the intent of the programmer.
- Minimizes the number of classes and methods.

### Simple Design Rule 1: Runs All the Tests

- Making our systems testable pushes us toward a design where our classes are small and single purpose.
- The more tests we write, the more we’ll continue to push toward things that are simpler to test.
- Tight coupling makes it difficult to write tests.

### Simple Design Rule 2-4: Refactoring

- The fact that we have these tests eliminates the fear that cleaning up the code will break it!
- We can increase cohesion, decrease coupling, separate concerns, modularize system concerns, shrink our functions and classes, choose better names, and so on.
- This is also where we apply the final three rules of simple design: Eliminate duplication, ensure expressiveness, and minimize the number of classes and methods.

### No Duplication

- Duplication causes additional work, additional risk, and additional unnecessary complexity.
- Creating a clean system requires the will to eliminate duplication, even in just a few lines of code.

### Expressive

- It is easy to write code we undestand, because we understand the problem we're trying to solve at that time but other maintainers don't.
- You can express yourself by choosing good names. We want to be able to hear a class or function name and not be surprised when we discover its responsibilities.
- You can also express yourself by keeping your functions and classes small. Small classes and functions are usually easy to name, easy to write, and easy to understand.
- You can also express yourself by using standard nomenclature. Design patterns, for example, are largely about communication and expressiveness.
- Well-written unit tests are also expressive. A primary goal of tests is to act as documentation by example. Someone reading our tests should be able to get a quick understanding of what a class is all about.
- But the most important way to be expressive is to try.

## Chapter 13 - Concurrency

“Objects are abstractions of processing. Threads are abstractions of schedule.”

### Why Concurrency?

- Concurrency is a decoupling strategy. It helps us decouple `what` gets done from `when` it gets done.
- In single-threaded applications `what` and `when` are so strongly coupled that the state of the entire application can often be determined by looking at the stack backtrace.
- Consider a system that handles one user at a time and requires only one second of time per user. This system is fairly responsive for a few users, but as the number of users increases, the system’s response time increases. No user wants to get in line behind 150 others! We could improve the response time of this system by handling many users concurrently.

#### Myths and Misconceptions

Concurrency is `hard`. If you aren’t very careful, you can create some very nasty situations. Consider these common myths and misconceptions:
- Concurrency always improves performance. Not always!, concurrency can sometimes improve performance, but only when there is a lot of wait time that can be shared between multiple threads or multiple processors.
- Design does not change when writing concurrent programs. Not true!, In fact, the design of a concurrent algorithm can be remarkably different from the design of a single-threaded system. The decoupling of what from when usually has a huge effect on the structure of the system.
- Understanding concurrency issues is not important when working with a container such as a Web or EJB container. Still not true!, In fact, you’d better know just what your container is doing and how to guard against the issues of concurrent update and deadlock.

Here are a few more balanced sound bites regarding writing concurrent software:
- Concurrency incurs some overhead, both in performance as well as writing additional code.
- Correct concurrency is complex, even for simple problems.
- Concurrency bugs aren’t usually repeatable, so they are often ignored as one-offs2 instead of the true defects they are.
- Concurrency often requires a fundamental change in design strategy.

### Concurrency Defense Principles

#### Single Responsibility Principle

Keep your concurrency-related code separate from other code.

#### Corollary: Limit the Scope of Data

Take data encapsulation to heart, severely limit the access of any data that may be shared.

#### Corollary: Use Copies of Data

- In some situations it is possible to copy objects and treat them as read-only.
- In other cases it might be possible to copy objects, collect results from multiple threads in these copies and then merge the results in a single thread.

#### Corollary: Theads Should Be as Independent as Possible

Consider writing your threaded code such that each thread exists in its own world, sharing no data with any other thread. Each thread processes one client request, with all of its required data coming from an unshared source and stored as local variables.

### Beware Dependencies Between Synchronized Methods

Avoid using more than one method on a shared object but there will be times when you must use more than one method on a shared object. When this is the case, there are three ways to make the code correct:
- **Client-Based Locking**: Have the client lock the server before calling the first method and make sure the lock’s extent includes code calling the last method.
- **Server-Based Locking**: Within the server create a method that locks the server, calls all the methods, and then unlocks. Have the client call the new method.
- **Adapted Server**: Create an intermediary that performs the locking. This is an example of server-based locking, where the original server cannot be changed.

### Keep Synchronized Sections Small

### Writing Correct Shut-Down Code Is Hard

Think about shut-down early and get it working early. It’s going to take longer than you expect. Review existing algorithms because this is probably harder than you think.

### Testing Threaded Code

- Write tests that have the potential to expose problems and then run them frequently, with different programatic configurations and system configurations and load. If tests ever fail, track down the failure. Don’t ignore a failure just because the tests pass on a subsequent run.
- Treat spurious failures as candidate threading issues. Do not ignore system failures as one-offs.
- Get your nonthreaded code working first. Do not try to chase down nonthreading bugs and threading bugs at the same time. Make sure your code works outside of threads.
- Make your threaded code pluggable. Make your thread-based code especially pluggable so that you can run it in various configurations.
- Make your threaded code tunable.
- Run with more threads than processors.
- Run on different platforms. Run your threaded code on all target platforms early and often.
- Instrument your code to try and force failures.

## Chapter 14 - 16

These 3 chapters are Java code example and case studies

## Chapter 17 - Smells and Heuristics

### Comments

#### C1: Inappropriate Information

It is inappropriate for a comment to hold information better held in a different kind of system such as your source code control system, your issue tracking system, or any other record-keeping system.

#### C2: Obsolete Comment

Comments get old quickly. It is best not to write a comment that will become obsolete. If you find an obsolete comment, it is best to update it or get rid of it as quickly as possible.

#### C3: Redundant Comment

A comment is redundant if it describes something that already describes itself. For example: `i++; // increment i`

#### C4: Poorly Written Comment

If you are going to write a comment, take the time to make sure it is the best comment you can write. Choose your words carefully. Use correct grammar and punctuation.

#### C5: Commented-Out code

Commented-out code is an abomination. When you see commented-out code, delete it! Don’t worry, the source code control system still remembers it.

### Environment

#### E1: Build Requires More Than One Step

Building a project should be a single trivial operation. You should not have to check many little pieces out from source code control. 

#### E2: Tests Require More Than One Step

You should be able to run all the unit tests with just one command. In the best case you can run all the tests by clicking on one button in your IDE. In the worst case you should be able to run a single simple command in a shell.

### Functions

#### F1: Too Many Arguments

Functions should have a small number of arguments. No argument is best. More than three is very questionable and should be avoided.

#### F2: Output Arguments

Output arguments are counterintuitive. Readers expect arguments to be inputs, not outputs. If your function must change the state of something, have it change the state of the object it is called on.

#### F3: Flag Arguments

Boolean arguments declare that the function does more than one thing. They are confusing and should be eliminated.

#### F4: Dead Function

Methods that are never called should be discarded.

### General

#### G1: Multiple Languages in One Source File

The ideal is a source file to contain one, and only one, language.

#### G2: Obvious Behavior Is Unimplemented

Following “The Principle of Least Surprise”, any function or class should implement the behaviors that another programmer could reasonably expect.

#### G3: Incorrect Behavior at the Boundaries

There is no replacement for due diligence. Every boundary condition, every corner case, every quirk and exception represents something that can confound an elegant and intuitive algorithm. Don’t rely on your intuition. Look for every boundary condition and write a test for it.

#### G4: Overridden Safeties

Turning off certain compiler warnings (or all warnings!) may help you get the build to succeed, but at the risk of endless debugging sessions. Turning off failing tests and telling yourself you’ll get them to pass later is as bad as pretending your credit cards are free money.

#### G5: Duplication

- This is one of the most important rules in this book, and you should take it very seriously.
- Every time you see duplication in the code, it represents a missed opportunity for abstraction.
- The most obvious form of duplication is when you have clumps of identical code that look like some programmers went wild with the mouse, pasting the same code over and over again. These should be replaced with simple methods.

#### G6: Code at Wrong Level of Abstraction

- It is important to create abstractions that separate higher level general concepts from lower level detailed concepts. For example, constants, variables, or utility functions that pertain only to the detailed implementation should not be present in the base class. The base class should know nothing about them.
- Isolating abstractions is one of the hardest things that software developers do, and there is no quick fix when you get it wrong.

#### G7: Base Classes Depending on Their Derivatives

The most common reason for partitioning concepts into base and derivative classes is so that the higher level base class concepts can be independent of the lower level derivative class concepts. Therefore, when we see base classes mentioning the names of their derivatives, we suspect a problem. In general, base classes should know nothing about their derivatives.

#### G8: Too Much Information

- Well-defined modules have very small interfaces that allow you to do a lot with a little.
- Hide your data, utility functions, constants and your temporaries.
- Don’t create classes with lots of methods or instance variables.
- Don’t create lots of protected variables and functions for your subclasses.
- Concentrate on keeping interfaces very tight and very small. Help keep coupling low by limiting information.

#### G9: Dead Code

The problem with dead code is that after awhile it starts to smell. This is because dead code is not completely updated when designs change. It still compiles, but it does not follow newer conventions or rules. When you find dead code, delete it from the system.

#### G10: Vertical Separation

- Variables and function should be defined close to where they are used.
- Local variables should be declared just above their first usage and should have a small vertical scope.
- Private functions should be defined just below their first usage. Private functions belong to the scope of the whole class, but we’d still like to limit the vertical distance between the invocations and definitions. Finding a private function should just be a matter of scanning downward from the first usage.

#### G11: Inconsistency

- If you do something a certain way, do all similar things in the same way.
- Be careful with the conventions you choose, and once chosen, be careful to continue to follow them.

#### G12: Clutter

Variables that aren’t used, functions that are never called, comments that add no information, and so on. All these things are clutter and should be removed.

#### G13: Artificial Coupling

In general an artificial coupling is a coupling between two modules that serves no direct purpose. It is a result of putting a variable, constant, or function in a temporarily convenient, though inappropriate, location. This is lazy and careless.

#### G14: Feature Envy

When a method uses accessors and mutators of some other object to manipulate the data within that object, then it `envies` the scope of the class of that other object. It wishes that it were inside that other class so that it could have direct access to the variables that manipulating.

#### G15: Selector Arguments

Selector arguments is difficult to remember and each selector argument combines many function into one. Selector arguments are just a lazy way to avoid splitting a large function into several smaller functions.

#### G16: Obscured Intent

We want code to be as expressive as possible. It is worth taking the time to make the intent of our code visible to our readers.

#### G17: Misplaced Responsibility

One of the most important decisions a software developer can make is where to put code. The principle of least surprise comes into play here. Code should be placed where a reader would naturally expect it to be. One way to make this decision is to look at the names of the functions.

#### G18: Inappropriate Static

In general you should prefer nonstatic methods to static methods. When in doubt, make the function nonstatic. If you really want a function to be static, make sure that there is no chance that you’ll want it to behave polymorphically.

#### G19: Use Explanatory Variables

One of the most powerful ways to make a program readable is to break the calculations up into intermediate values that are held in variables with meaningful names.

#### G20: Function Names Should Say What They Do

If you have to look at the implementation (or documentation) of the function to know what it does, then you should work to find a better name or rearrange the functionality so that it can be placed in functions with better names.

#### G21: Understand the Algorithm

- Before you consider yourself to be done with a function, make sure you understand how it works. It is not good enough that it passes all the tests. You must know that the solution is correct.
- The best way to gain this knowledge and understanding is to refactor the function into something that is so clean and expressive that it is obvious how it works.

#### G22: Make Logical Dependencies Physical

If one module depends upon another, that dependency should be physical, not just logical. The dependent module should not make assumptions (in other words, logical dependencies) about the module it depends upon. Rather it should explicitly ask that module for all the information it depends upon.

#### G23: Prefer Polymorphism to If/Else or Switch/Case

`ONE SWITCH` rule: There may be no more than one switch statement for a given type of selection. The cases in that switch statement must create polymorphic objects that take the place of other such switch statements in the rest of the system.

#### G24: Follow Standard Conventions

- Every team should follow a coding standard based on common industry convention.
- This coding standard should specify things like where to declare instance variables; how to name classes, methods, and variables; where to put braces; and so on.
- The team should not need a document to describe these conventions because their code provides the examples.

#### G25: Replace Magic Numbers with Named Constants

In general it is a bad idea to have raw numbers in your code. You should hide them behind well-named constants.

#### G26: Be Precise

When you make a decision in your code, make sure you make it `precisely`. Know why you have made it and how you will deal with any exceptions. Don’t be lazy about the precision of your decisions. For example, if you decide to call a function that might return null, make sure you check for null.

#### G27: Structure over Convention

Enforce design decisions with structure over convention. Naming conventions are good, but they are inferior to structures that force compliance.

#### G28: Encapsulate Conditionals

Boolean logic is hard enough to understand without having to see it in the context of an if or while statement. Extract functions that explain the intent of the conditional.

```java
// Bad
if (shouldBeDeleted(timer))

// Good
if (timer.hasExpired() && !timer.isRecurrent())
```

#### G29: Avoid Negative Conditionals

Negatives are just a bit harder to understand than positives. So, when possible, conditionals should be expressed as positives.

```java
// Bad
if (buffer.shouldCompact())

// Good
if (!buffer.shouldNotCompact())
```

#### G30: Functions Should Do One Thing

Functions that do more than one thing should be converted into many smaller functions, each of which does one thing.

#### G31: Hidden Temporal Couplings

Temporal couplings are often necessary, but you should not hide the coupling. Structure the arguments of your functions such that the order in which they should be called is obvious.

#### G32: Don't Be Arbitrary

Have a reason for the way you structure your code, and make sure that reason is communicated by the structure of the code. If a structure appears arbitrary, others will feel empowered to change it. If a structure appears consistently throughout the system, others will use it and preserve the convention.

#### G33: Encapsulate Boundary Conditions

Boundary conditions are hard to keep track of. Put the processing for them in one place. Don’t let them leak all over the code.

#### G34: Functions Should Descend Only One Level of Abstraction

The statements within a function should all be written at the same level of abstraction, which should be one level below the operation described by the name of the function.

#### G35: Keep Configurable Data at High Levels

If you have a constant such as a default or configuration value that is known and expected at a high level of abstraction, do not bury it in a low-level function. Expose it as an argument to that low-level function called from the high-level function.

#### G36: Avoid Transitive Navigation

In general we don’t want a single module to know much about its collaborators. More specifically, if A collaborates with B, and B collaborates with C, we don’t want modules that use A to know about C. If many modules used some form of the statement `a.getB().getC()`, then it would be difficult to change the design and architecture to interpose a Q between B and C.

### Names

#### N1: Choose Descriptive Names

Don’t be too quick to choose a name. Make sure the name is descriptive. Remember that meanings tend to drift as software evolves, so frequently reevaluate the appropriateness of the names you choose. You need to take the time to choose them wisely and keep them relevant.

#### N2: Choose Names at the Appropriate Level of Abtraction

Don’t pick names that communicate implementation. Instead, choose names the reflect the level of abstraction of the class or function you are working in.

#### N3: Use Standard Nomenclature Where Possible

Names are easier to understand if they are based on existing convention or usage. For example, if you are using the `DECORATOR` pattern, you should use the word Decorator in the names of the decorating classes.

#### N4: Unambiguous Names

Choose names that describes how function work.

#### N5: Use Long Names for Long Scope

The length of a name should be related to the length of the scope. You can use very short variable names for tiny scopes, but for big scopes you should use longer names. Variable names like `i` and `j` are just fine if their scope is five lines long.

#### N6: Avoid Encodings

Names should not be encoded with type or scope information. Prefixes such as `m_` or `f` are useless.

#### N7: Names Should Describe Side-Effects

- Names should describe everything that a function, variable, or class is or does. Don’t hide side effects with a name.
- Don’t use a simple verb to describe a function that does more than just that simple action.

### Tests

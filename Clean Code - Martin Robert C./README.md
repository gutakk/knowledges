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

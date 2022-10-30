## Introduction
In current era of programming, functions are the constituent of a program.
In this chapter we will discuss how can we write them well.

## Small !!

- The first rule of functions is that the should be small. The second rule of functions is that they should be smalle than that.
- Functions should hardly ever be 20 lines long


## Blocks and Indenting

- Blocks within *if* statements, *else* statements, *while* statements and so on should be one loine long.
- Probably that line should be a function call. \n
**CS_3.1**
``` 
public static String renderPageWithSetupsAndTeardowns( 
  PageData pageData, 
  boolean isSuite) throws Exception { 
    if (isTestPage(pageData))
      includeSetupAndTeardownPages(pageData, isSuite); 
    return pageData.getHtml();
}
```

- Functions should not be large enough to hold nested structures.
- Therefore, the indent level of a functions should not be greater than one or two.
- These practices make the functions easier to read and understand.

## Do One Thing

- Functions should do one thing. They should do it well. They should do it only.
- We can say that CS_3.1 is doing three things:
1. Determining whether the page is a test page
2. If so, including setups and terdowns.
3. Rendering the page in HTML
- But this not a case, the three steps of the function are onel evel of abstraction below the stated name of the function.
- If a function does only those steps that are one level below the stated name of the function, then the function is doing one thing. 
- So another way to know that a fucntion is doing more than "one thing" is if you can extract another function from it with a name that is not merely a restatement of its implementation.
- One other way to identify that function is doing more than one thing: if function is divided into sections. It means: Functions that do one thing cannot be resonable divided into sections.

## Reading Code from Top to Bottom: *The Stepdown Rule*

- Code should be in such a way it can be read like a top-down narrative.
- Every function to be followed by those at the next level of abstractions so that  we can read teh program, descending one level of abstraction at a time as we read down the list of functions.

## Switch Statements

- It's hard to make a *switch* statement that does one thing. By their nature, switch statemtns always do N things.
- We can't always avoid Switch statements, but we can make sure that each *switch* statement is buried in a low-level class and is never repeated. We do this, of course, with polymorphism.
- Consider this code snippet:
**CS_3.2:**
```
public Money calculatePay(Employee e) throws InvalidEmployeeType {
  switch (e.type) { 
    case COMMISSIONED:
      return calculateCommissionedPay(e); 
    case HOURLY:
      return calculateHourlyPay(e); 
    case SALARIED:
      return calculateSalariedPay(e); 
    default:
      throw new InvalidEmployeeType(e.type);
   }
  }
```
- There are several problems with this function:
1. When new employees are added, it will grow.
2. It very clearly does more than one thing.
3. It violates Single Responsibility Principle(SRP), because there is more than one reason for it to change.
4. It violates Open Closed Principle, because it must change whenever new types are added.
5. But possibly the worst problem with this function is that there are an unlimited number of other fucntions that will have the same structure.
```
isPayday(Employee e, Date date)

Or

deliveryPay(Employee e, Money pay)
```
- The solution to this problem is to bury the *switch* statement in the basement of an ABSTRACT FACTORY and never let anyone see.
- Author's general rule for *switch* statements is that they can be tolerated if they appear only once, are used to create polymorphic objects, and are hidden behind an inheritance relationship so that the rest of the system can't see them. 

- **Of course every circumstance is unique, and there may be times we can violate one or more parts of that rule.**

## Use Descriptive Names

- The smaller and more focused a function is, the easier it is to choos a descriptive name.
- A long descriptive name is better than a short enigmatic name.
- A long descriptive name is better than a long descriptive comment. 
- Us a nameing convention that allows multiple words to give the function a name that says what it does.
- Choosing descriptive names will clarify the design of htemoudle in your midn and help you to improve it. It is not at all uncommon that hunting for a good name results in a favorable resturcturing of the code.
- Be consistent in your names. Use the same phrases, nouns, and verbs in the function names you choose for your modules.

## Function Arguments

- The ideal number of arguments for a function is zero (niladic). 
- Next comes, monadic and dyadic.
- Three arguments should be avoided where possible. More than three requires very special justification and then shouldn't be used anyway.
- Arguments are hard. They take a lot of conceptul power. 
- The argument is at a different level of abstraction than the function name and forces you to know a detail that isn't particularly important at that point.
- Arguments are even harder from a testing point of view. Imagine the difficultyof writing all the test cases to ensure that all the various combinations of arguments work properly.
- If there are no arguments, this is trivial.
- If there's one argument, it's not too hard.
- With two arguments the problem gets a bit more challenging. With more than two arguments, testing every combination of appropriate values can be daunting.


## Common Monadic Forms

- There are two very common reasons to pass a single argument into a function:
 1. You may be asking  a question about that argument as in ``` boolean fileExists("MyFile") ```
 2. You may be operating on that argument, transforming it into something eles and returning it, for example ``` InputStream fileOpen("MyFile")  ``` transforms a file name String ito an InputStream return value.
- A somewhat less common, but still very useful for a single argument function, is  an event. In this form there is an input argument but no output argument. The overall program is meant to interpret the function call as an event and use teh argument to alter the state of the system.
-  Using an output argument instead of a return value for a transformation is confusing. If a function is going to transform its input argument, the transformation should appear as the return value.

## Flag Arguments

- Flag arguments are ugly. It immediatley complicates the signature of the method, loudly proclaiming that this function does more than one thing. It does one thing if the flag is true and another if the flag is false!

## Dyadinc Functions

- A function with two arguments is harder to understatnd than a monadic function.
- Even obvious dyadic functions like ``` assertEquals(expected, actual) ``` are problematic. 
- The two arguments have no natural ordering. The ``` expected, actual ``` ordering is a convention that requires practice to learn.
- Dyads aren't evil, and you will certainly have to write them.
- However, you should be aware that they come at a cost and should take advantage of what mechanisms may be available to you to convert them into monads.


## Triads
- Function that tke three argumetns are significantly harder to understand that dyads


## Argument Objects

- When a fucntion seems to need more than two or three arguments, it is likely that some of those arguments ought to be wrapped into a class of their own.
Consider the following example, the difference between the two following declarations:

```
Circle makeCircle(double x, double y, double radius);
Circle makeCircle(Point center, double radius);

```
## Argument Lists

- If the variable arguments are all treated identically, as they are in the example above, then they are equivalent to a single argument of type ```List```. 
- Example:
```
void monad(Integer... args);
void dyad(String name, Integer... args);
void triad(String name, int count, Integer... args);
```

## Verbs and Keywords

- Choosing good names for a function can go a long way toward explaining the intent of the function and the order and intent of the arguments. In the case of a monad, the function and argument should for a very nice verb/noun pair. 
- For example: ``` write(name)``` is very evocative. An even better name might be ``` writeFiled(name) ```, which tells us that the "name" thing is a "field".
- This last is an example fo the *keyword* form of a function name. Using this form we encode the names of the arguments into the function name. For example ```assertEquals``` might be better written as ```assertExpectedEqualsActual(expected, actual)```. This strongly mitigates the problem of having to remember the ordering of the arguments.

## Have No Side Effects

- Side effects are lies. Your function promises to do one ting, but it also does other *hidden* things. Sometimes it will make unexpected changes to the variables of its own class. Sometimes it will make them to the parameters passed into the function or to sysyem globals. In either case the are devious and damging mistruths that often result in strange temporal couplings and order dependencies.

## Output Arguments

- Arguments are most naturally interpreted as inputs to a function. If you have been programming for more than few years, you've done a doubl-take on an argument that was actually an output rather than an input. 
- In general output arguments should be avoided, If your function must change the state of something, have it change the state of its owning object.

## Command Query Separation

- Functions should either do something or answer something, but not both. Either your function should change the state of an object.
- Consider the following example:
``` public boolean set(String attribute, String value) ```
- This function sets the value fo a named attribute and returns ``` true``` if it is successful and ``` false ``` if no such attributes exists.
- The real solution is to separate the command from the query so that the ambiguity cannot occur.
```
if (attributeExists("username")) { 
   setAttribute("username", "unclebob"); ...
}
```

## Prefer Exceptions to Returning Error Codes

- Returning error codes from command functions is a subtle violation of command query separation. It promotes commands being used as expressions in the predicates of ``` if ``` statements.

- On the other hand, if you use exceptions instead of returned error codes, then the error processing code can be separated from the happy path code and can be simplified:

``` 
try {
  deletePage(page); 
  registry.deleteReference(page.name); 
  configKeys.deleteKey(page.name.makeKey());
}
catch (Exception e) {
  logger.log(e.getMessage()); 
}
```
## Extract Try/Catch blocks

```Try/catch``` blocks are ugly in their own right. They confuse the structure of the code and mix error processing with normal processing. So it is better to extract the bodies of the ```try``` and ```catch``` blocks out into functions of their own.

```
public void delete(Page page) {
  try {
    deletePageAndAllReferences(page); 
  }
  catch (Exception e) { 
    logError(e);
  } 
}

private void deletePageAndAllReferences(Page page) throws Exception { 
   deletePage(page);
   registry.deleteReference(page.name);
   configKeys.deleteKey(page.name.makeKey());
}

private void logError(Exception e) { 
    logger.log(e.getMessage());
}
```
## Error Handling is One thing

- Functions should do one thing, Error hadling is one thing. Thus a functions that handles errors should do nothing else. This implies (as in the example above) that if the keyword ```try``` exists in a function, it should be very first word in the function and that there should be nothing after the ```catch/finally``` blocks.

## Don't Repeat Yourself

- Duplication may be the root of all evil in software. Many principles and practices have been created for the purpose of controlling or eliminating it.


## How do you write functions like this?

- Writing software is like any other kind of writing. When you write a paper or an article, you get your thoughts down first, then you mssage it until it reds well. The first draft might be clumsy and disorganized, so you wordsmith it and restructure it and refine it until it reads the way you want it to read.


## Conclusion

- Master programmers think of systems as stories to be told rather than programs to be written.

- After following rules, the functions will be short, well named and nicely organized. But never forget that your real goal is to tell the story of the system. 





















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















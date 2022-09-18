## Introduction
In current era of programming, functions are the constituent of a program.
In this chapter we will discuss how can we write them well.

## Small !!

- The first rule of functions is that the should be small. The second rule of functions is that they should be smalle than that.
- Functions should hardly ever be 20 lines long


## Blocks and Indenting

- Blocks within *if* statements, *else* statements, *while* statements and so on should be one loine long.
- Probably that line should be a function call.
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
- 


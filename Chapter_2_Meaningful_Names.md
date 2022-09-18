# Introduction

In software development cycle, we always need to give name at multiple instances. We need to give names for repositories, directories, files, class, variable, functions etc.
We have to follow some simple rules for creating good names:

## Use Intention Revealing names

-  Name should tell you why it exists, what it does, and how it is used.
If name requires comment then the name does not reveal it intent.


## Avoid Disinformation
-  Don't make common abbriviations as variable name 
-  Don't use lowercase 'l' or uppercase 'O' it may be confusing.


## Make meaningful Distinctions

-  Number-series naming is the opposite of intentional naming. Such names are not disninformative-- they are noninformative.
-  Noise words are redundant. e.g ProductInfo or ProductData are same so these should not be used in same codespace as they don't give different meaning.


## Use pronounceable names

- *Self Explainable*

## Use Searchable Names

- Single-letter names can be used only as a local variable inside short methods.  It should not be used for the variable having larger scope.
- The length of a name should correspond to the size of its scope.
- Use constant names for constant such that they can be searchable.

## Avoid Encoding

- Encoded names are seldom pronounceable and are easy to mis-type.

## Member Prefixes

- We don't need to prefix member variable with 'm_'


## Interfaces and Implementation

- The factory calss will be an interface and will be implemented by a convrete class.
- So, we can have ShapeFactory Interface and ShapeFactoryImpl is its implementation, here we can use encoding.


## Avoid mental mapping

- Readers shouldn't ahve to mentally translate your names into other names they already know.
- If variable name is 'a' or 'a2' then ask yourself why it can't be 'b' or 'c' or 'a200', if there is no concrete answer then it means you should change your variable name.
- Smart people sometimes like to show off their smarts by demosntrating their mental juggling abilities, we should avoid to show off for keeping variable names.
- One difference between a smart programmer and a professional programmer is that the professional understands that clarity is king. Professionals use their powers for good and wirte code that others can understand.

## Class Names

- Classes and objects should have noun or noun phrase names like 'Customer', 'WikiPage', 'Account'.
- Avoid words like 'Manager', 'Processor', 'Data' or 'Info' in the name of a class.
- A class name should not be a verb.

## Method Names

- Methods should have verb or verb phrase names like 'postpayment', 'deletePage', or ''save',
- When constructors are overloaded, use static factory methods with names that describe the arguments. For example,
*Complex fulcrumPoint = Complex.FromRealNumber(23.0);*
is generally better than
*Complex fulcrumPoint = new Complex(23.0);*
Consider enforcing their use by making the corresponding constructors private.

## Don't be cute

- Say what you mean. Mean what you say.

## Pick one word per concept

- Likewise, it’s confusing to have a controller and a manager and a driver in the same code base.
- A consistent lexicon is a great boon to the programmers who must use your code.

## Don't Pun

- Avoid using the same word for two purposes. Using the same term for two different ideas is essentially a pun.
- Our goal, as authors, is to make our code as easy as possible to understand. We want our code to be a quick skim, not an intense study. We want to use the popular paperback model whereby the author is responsible for making himself clear and not the academic model where it is the scholar’s job to dig the meaning out of the paper.

## *Kabhi* Use Solution Domain names *Kabhi* Use Problem Domain Names

- Remember that the people who read your code will be programmers. So go ahead and use computer science (CS) terms, algorithm names, pattern names, math terms, and so forth. It is not wise to draw every name from the problem domain because we don’t want our coworkers to have to run back and forth to the customer asking what every name means when they already know the concept by a different name.

- Separating solution and problem domain concepts is part of the job of a good pro- grammer and designer. The code that has more to do with problem domain concepts should have names drawn from the problem domain.
- When there is no “programmer-eese” for what you’re doing, use the name from the prob- lem domain. At least the programmer who maintains your code can ask a domain expert what it means.

## Add meaningful context


## Don’t Add Gratuitous Context


## Final Words

- The hardest thing about choosing good names is that it requires good descriptive skills and a shared cultural background. This is a teaching issue rather than a technical, business, or management issue. As a result many people in this field don’t learn to do it very well.
- Follow some of these rules and see whether you don’t improve the readability of your code. If you are maintaining someone else’s code, use refactoring tools to help resolve these problems. It will pay off in the short term and continue to pay in the long run.






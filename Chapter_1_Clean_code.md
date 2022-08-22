# Clean Code

## Introduction

After reading this book:

1. We will know lot about code
2. We'll be able to tell the difference between good code and bad code
3. We'll know how to write good code
4. We'll know how to transform bad code into good code.

## There will be code

- Remember that code is really the language in which we ultimately express the requirements.
We may create languages that are closer to the requirements. we may create tools that help us parse and assemble those requirements into formal structures.
But we will never eliminate necessary prescision- so there will always be code.


## Bad Code

- We all must have to go through bad code while our programming journey
- But we still write bad code and leave it for another day
- We generally decide that working mess is better than nothing
- Remember: **Later equals never**


## The Total Cost of Owning a Mess

- As the mess builds, the productivity of the team continues to decrease, asymptotically approaching zero.
- Every programmer have probably been slowed down by someone else's messy code or self messy code.
- In messy code, every change we make to the code breaks two or three other parts of the code.


### The Grand Redesign in the Sky

- Eventually the team rebels. They inform management that they cannot continue to develop in this odious code base. They demand a redesign.
- But redesigning the code and maintaining the old code, and sufficing the new requirements at the same time takes a lot of time.
During this long timespan, new codebase could also become messy. Then old team member starts leaving the organisation.
- So keeping code clean is not just cost effective; it's matter of professional survival.


### Attitude

We can say that following reasons are there to turn good code into bad code:

- We complain that the requirements changed in ways that thwart the original design.
- We bemoan the schedules that were too tight to do the things right
- We blather abotu stupid managers and intolerant customers and useless marketing types.

But fault is not in others but in ourselves. We are unprofessionals.

- We should not be shy about telling them what we think.
- Most managers want the truth, even when the don't act like it.
- They may defend the schedule and requirements with passion; but that's their job.
- It's our job to defend the code with equal passion.

Conclusion:
- So too it is unprofessional for programmers to bend to the will of managers who don't understand the risks of making messes.


### The Primal Conundrum

- The only waty to make the deadline - the only way to go fast - is to keep the code as clean as possible at all times.

### The Art of Clean Code

- If we want to write clean code then first we need to know what is Clean code
- Being able to recognize clean code from dirty code does not mean that we knwo how to write clean code.
- Writing clean code requires the disciplined use of a  myriad little techniques applied through a panstakngly acquired sense of "cleanliness". This "code-sense" is the key.
- In short, a programmer who writes clean code is an artist who can take a blank screen through a series of transformations until it is an elegantly coded system.


### What is clean code?

- Author asked this question to deeply experienced programmers what they thought:

  - Bjarne Stroustrup: "I like my code to be elegant and efficient. The logic should be straightforward to make it hard for bugs to hide, the dependencies minimal to ease maintenance, error handling complete according to an articulated strategy, and per- formance close to optimal so as not to tempt people to make the code messy with unprinci- pled optimizations. Clean code does one thing well."

  - Grady Booch: "Clean code is simple and direct. Clean code reads like well-written prose. Clean code never obscures the designer’s intent but rather is full of crisp abstractions and straightforward lines of control."

  - Dave Thomas: "Clean code can be read, and enhanced by a developer other than its original author. It has unit and acceptance tests. It has meaningful names. It provides one way rather than many ways for doing one thing. It has minimal depen- dencies, which are explicitly defined, and pro- vides a clear and minimal API. Code should be literate since depending on the language, not all necessary information can be expressed clearly in code alone."

  - Michael Feathers: "I could list all of the qualities that I notice in clean code, but there is one overarching quality that leads to all of them. Clean code always looks like it was written by someone who cares. There is nothing obvious that you can do to make it better. All of those things were thought about by the code’s author, and if you try to imagine improvements, you’re led back to where you are, sitting in appreciation of the code someone left for you—code left by some- one who cares deeply about the craft."

### Schools of Thought

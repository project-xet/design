# Goals

The aim of the Xet project isn't to simply implement novel patterns. It's design is driven by specific goals.

- Testability
- Safety
- Scalability
- Organisation

## Testability

This is obviously an important feature. Enabling automated testing helps a project grow and eases maintenance immensely. However, there are some impediments to testing that make it more difficult.

The first is the use of ambient state. Many frameworks are implemented in imperative languages and use ambient state to expose functionality like configuration and persistence. Setting up a testing environment involves scaffolding this state in some form. This tends to be cumbersome and difficult to do.

The second issue is one of hard-dependencies. Often application code is written in a way that results in it depending on specific implementations. For example,

Details of this will be discussed later in the design section, but briefly, Xet will attempt to address these issues with a few specific choices:

- Use protocols rather than concrete types
- Functions should only depend on their arguments

Protocols can be satisfied with either a test or real, working version of a type. Couple this with functions that only depend on their arguments and you have a very simple mechanism for setting up tests.

That's just one example for illustration. The Design documentation goes into more detail.

## Safety

This comes down to a few choices. The first is language. Xet will be coded in Swift. Dynamic languages are not a good choice. The debate over dynamic vs. static typing is almost of a religious nature; this document isn't going to delve into that. Instead we will discuss the positive aspects of static typing and how Xet can exploit it for safety.

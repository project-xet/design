# Design

## Units of Abstraction

As much as possible, Xet eschews reference types and relies on functions and value types as the primary unit of abstraction. This means no inheritance, which is a clumsy method for sharing functionality and makes a good deal of behaviour implicit. It also allows an emphasis on smaller, focused bits of code; easier to reason about and easier to compose.

## Banning Ambient State

One of the biggest sins in many frameworks is giving units within the framework configuration and access to persistence via ambient state.

## Dependencies

In order to satisfy a request the service layer has a number of dependencies. For example, most applications will require a persistence layer of some kind, perhaps access to an SQL database. It's common to access a global reference of some kind in order to get DB access. However this inhibits testability, requiring either the scaffold of fixture data or pervasive stubbing.

Instead Xet will encapsulate dependencies in a container. However, unlike most dependency injection frameworks, Xet's approach is mostly a pattern rather than concrete code. Essentially it's a set of structs and protocols. There are a few principles:

- Be light weight
- No laziness
- No circular dependencies; these are satisfied by arguments to functions
- Uses let properties; no optionals, no type-casting
- No actual framework code, it's just a pattern

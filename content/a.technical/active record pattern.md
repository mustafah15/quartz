---
tags:
  - book-notes
  - ddd
parent: "[[lddd - implementing simple business logic]]"
type: literature
deeper: "[[when to use active record pattern]]"
---
"An Object that wraps a row in a database table or view encapsulates the database access and adds domain logic on that data" -Martin Fowler

Like the [[transaction script pattern]] active record supports cases where the business logic is simple however the business logic may operate on a more complex data structure, for example instead of flat records we can have more complicated object trees and hierarchies (relations)

operating on such data structure via a simple transaction script would result in lots of repetitive code the mapping of the data to an in-memory representation would be duplicated all over


### Implementation 
Consequently, this pattern uses dedicated objects known as active records to represent a complicated data structure, Apart from the data structure, these objects also implement data access methods for creating, reading updating, and deleting records as a result the active record objects are coupled to an ORM or some other data access framework, the pattern name is derived from the fact that each data structure is "active" that is it implements the data access logic

The pattern goal is to encapsulate the complexity of mapping the in-memory object to the database schema, in addition to being responsible for persistency the active record objects can contain business logic for example validating new values assigned to the fields or even implementing business related procedures that manipulate an object data



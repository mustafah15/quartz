---
tags:
  - book-notes
  - software-design
parent: "[[causes of complexity]]"
aliases:
  - dependencies
type: literature
---
## dependencies
- a dependency exists when a given piece of code can not be understood and modified in isolation the code relates in some way to another code, and the other code must be considered modified if the given code is changed.
- dependencies are a fundamental part of software and can't be completely eliminated in fact we intentionally introduce dependencies as part of the software design process every time you write a new class you create dependencies around the API for that class however one of the goals of software design is to reduce the number of dependencies and to make the dependencies that remain as simple and obvious as possible.
---
tags:
  - system-design
type: literature
parent: "[[general purpose modules vs special purpose modules]]"
---

## Questions to help you find the right balance between [[general purpose approach]] and [[special purpose approach]]

- **What is the simplest interface that will cover all my current needs**? 
	- if you reduce the number of methods in an API without reducing the overall capabilities, then you are probably creating a more general-purpose method. Reducing the number of methods makes sense only as long as the API for each individual method stays simple; if you have to introduce lots of additional arguments in order to reduce the number of methods, then you may not really be simplifying things
- In how many situations will this method be used?
	- if a method is designed for one particular use it is a red flag that it may be too special purpose. see if you can replace several special methods with a single general-purpose method
- Is this API easy to use for my current needs?
	- This question can help you to determine when you have gone too far in making an API simple and general-purpose. If you have to write a lot of additional code to use a class for your current purpose, that's a red flag that the interface doesn't provide the right functionality

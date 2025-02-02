---
tags:
  - software-design
  - book-notes
parent: "[[information hiding and information leakage]]"
aliases:
  - information leakage
  - Information Leakage
type: literature
against: "[[information hiding]]"
---
the opposite of [[information hiding|information hiding]] is information leakage. 
**information leakage occurs when a design decision is reflected in multiple modules.** when this happens it creates a dependency between the modules as any change to that design decision will require changes to all of the involved modules. 
if a piece of information is reflected in the interface for a module then by definition it has been leaked that is why simpler interfaces tend to correlate with better information hiding. *HOWEVER*, information can be leaked even if it doesn't appear in a module interface. for example, suppose two classes both have knowledge of a particular file format even if neither class exposes that information in its interface, they both depend on the file format if the format changes, both classes will need to be modified. back door leakage like this is more pernicious than leakage through an interface because it isn't obvious.
information leakage is one of the most important red flags in software design. one of the best skills you can learn as a software designer is a high level of sensitivity to information leakage.


deeper:

- ### [[how to prevent information leakage]]
- ### [[information leakage types]]
